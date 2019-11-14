---
title: Creating Briefcase Reconcilers
description: A briefcase reconciler gives Briefcase the means to reconcile different versions of a document.
ms.assetid: 86d66291-96ae-40ea-98ef-ef263f25aa82
keywords:
- briefcase reconcilers
- reconciliation
- IReconcilableObject
- IReconcileInitiator
ms.topic: article
ms.date: 05/31/2018
---

# Creating Briefcase Reconcilers

A briefcase reconciler gives Briefcase the means to reconcile different versions of a document.

-   [About Briefcase Reconcilers](#about-briefcase-reconcilers)
    -   [Reconciliation](#reconciliation)
    -   [Creating a Briefcase Reconciler](#creating-a-briefcase-reconciler)
    -   [User Interaction in Reconciliation](#user-interaction-in-reconciliation)
    -   [Reconciling Embedded Objects](#reconciling-embedded-objects)
    -   [Residues](#residues)
-   [Briefcase Reconciler Reference](#briefcase-reconciler-reference)
    -   [Briefcase Reconciler Interfaces and Methods](#briefcase-reconciler-interfaces-and-methods)

## About Briefcase Reconcilers

A briefcase reconciler combines different input versions of a document to produce a single, new output version of the document. You might need to create a briefcase reconciler to support your type of document. This overview describes briefcase reconcilers and explains how to create them.

The following topics are discussed:

-   [Reconciliation](#reconciliation)
-   [Creating a Briefcase Reconciler](#creating-a-briefcase-reconciler)
-   [User Interaction in Reconciliation](#user-interaction-in-reconciliation)
-   [Reconciling Embedded Objects](#reconciling-embedded-objects)
-   [Residues](#residues)

### Reconciliation

A document is a collection of information that can be copied and changed. A document has different versions if the contents of at least two copies of the document are different. Reconciliation produces a single version of a document from two or more initial versions. Typically, the reconciled version is a combination of information from the initial versions with the most recent or most useful information preserved.

Reconciliation is initiated by Briefcase when it determines that two or more copies of the same document are different. Briefcase, which acts as the initiator in this context, locates and starts the briefcase reconciler associated with the given document type. The reconciler compares the documents and determines which portions of the documents to retain. Some reconcilers might require user interaction to complete reconciliation. Others might complete reconciliation without user interaction. The reconciler can be contained within an application or be an extension implemented as a DLL.

Some briefcase reconcilers might create residues. A residue is a document, usually having the same file type as the initial document, that contains information not saved in the merged version. Residues are typically used to give authors a quick way to determine what information from their original document is not in the final merged version. If a reconciler supports residues, it creates one residue for each of the original versions of the document. Residues are not created unless the initiator requests them.

Some briefcase reconcilers work with Briefcase to allow the user to terminate reconciliation. This is an important feature for a user who might decide that the reconciliation should not proceed. A reconciler typically provides a termination object when the reconciliation requires user interaction and might be lengthy. In some environments, a reconciler might allow partial reconciliation, enabling a user to temporarily suspend a reconciliation and resume it later. Briefcase does not currently support partial reconciliation, however.

### Creating a Briefcase Reconciler

You create a briefcase reconciler by implementing the reconciliation interfaces. At a minimum, a reconciler implements the [**IReconcilableObject**](https://msdn.microsoft.com/en-us/library/Bb761351(v=VS.85).aspx) interface and the [IPersistStorage](https://msdn.microsoft.com/library/ms679731(VS.85).aspx) or [IPersistFile](https://msdn.microsoft.com/library/ms687223(VS.85).aspx) interface. As the initiator, Briefcase determines when reconciliation is needed and calls the [**IReconcilableObject::Reconcile**](https://msdn.microsoft.com/en-us/library/Bb761353(v=VS.85).aspx) method to initiate reconciliation.

Although [**IReconcilableObject::Reconcile**](https://msdn.microsoft.com/en-us/library/Bb761353(v=VS.85).aspx) provides a wide-ranging set of reconciliation capabilities, a briefcase reconciler carries out only minimal reconciliation in most cases. In particular, Briefcase does not require the reconciler to support residue generation or to support the termination object. Also, the reconciler carries out a single top-to-bottom reconciliation and must not return the REC\_E\_NOTCOMPLETE value; that is, it should not attempt partial reconciliation.

Briefcase provides the [**IReconcileInitiator**](ireconcileinitiator.md) interface. The briefcase reconciler can use the [**IReconcileInitiator::SetAbortCallback**](https://msdn.microsoft.com/en-us/library/Bb761345(v=VS.85).aspx) method to set the termination object. Briefcase does not use version identifiers and cannot, therefore, provide previous versions of a document if a reconciler requests them using the corresponding methods in **IReconcileInitiator**.

Briefcase passes to [**IReconcilableObject::Reconcile**](https://msdn.microsoft.com/en-us/library/Bb761353(v=VS.85).aspx) file monikers representing the versions of the document to be reconciled. The briefcase reconciler gains access to the versions by using either the [IMoniker::BindToObject](https://msdn.microsoft.com/library/ms691433(VS.85).aspx) or [IMoniker::BindToStorage](https://msdn.microsoft.com/library/ms688738(VS.85).aspx) method. The latter is generally faster and is recommended. The reconciler must release any objects or storage to which it binds.

When the briefcase reconciler uses [IMoniker::BindToStorage](https://msdn.microsoft.com/library/ms688738(VS.85).aspx), it binds to storage that is either flat storage (a stream) or OLE-defined structured storage. If the reconciler expects flat storage, it should use IMoniker::BindToStorage to request the [IStream](https://msdn.microsoft.com/library/Aa380034(VS.85).aspx) interface. If the reconciler expects structured storage, it should request the [IStorage](https://msdn.microsoft.com/library/Aa380015(VS.85).aspx) interface. In both cases, it should request read-only direct (nontransacted) access to the storage; read/write access might not be available.

A minimal briefcase reconciler typically looks directly at the storage of the other versions and deals with embedded objects in a very primitive manner, such as merging two versions of the object by including both versions in the output version.

The initiator locates the appropriate briefcase reconciler by using a subset of the logic implemented by the [GetClassFile](https://msdn.microsoft.com/library/ms693715(VS.85).aspx) function to determine the type of a given file and then looks in the registry for the reconciler class associated with the given file type. Briefcase, like other Shell components, determines the type of a file solely by the file name extension. A file's extension must have a registered file type for Briefcase to invoke a reconciler for the file. You must set a registry entry of the following form when installing your reconciler.

```
CLSID
   {the file CLSID}
      Roles
         Reconciler
            (Default) = {the reconciler-classid}
```

The class must be quick loading, must be designated \_MULTIPLEUSE, and, unless marshalers are provided for the reconciliation interface, must be an in-process server (contained in a DLL) rather than a local server (implemented in an .exe file).

### User Interaction in Reconciliation

A briefcase reconciler should attempt to carry out reconciliation without user interaction. The more automated the reconciliation, the better the user's perception of the process.

In some cases, user intervention can be valuable. For example, a document system might require a user to review changes before accepting the merged version of a document or might require comments from the user explaining the changes that have been made. In these cases, the initiator, not the briefcase reconciler, is responsible for querying the user and carrying out the user's instructions.

In other cases, user intervention might be necessary—for example, when two versions have been edited in incompatible ways. In such cases, either the initiator or briefcase reconciler must query the user for instructions on how to resolve the conflict. In general, no initiator can rely on completing a reconciliation without expecting some user interaction. Reconcilers, on the other hand, have the option of interacting with the user to resolve conflicts or requiring the initiator to do so.

### Reconciling Embedded Objects

When reconciling a document, the briefcase reconciler itself can become an initiator if it discovers an embedded object of a type that it cannot reconcile. In this case, the reconciler needs to recursively reconcile each of the embedded objects and assume all the responsibilities of an initiator.

To carry out the recursion, the briefcase reconciler loads the object and queries for the appropriate interface. The handler for the object must support the interface. If any method of the interface returns the OLE\_E\_NOTRUNNING value, the reconciler must run the object in order to carry out the operation. Because code for embedded objects is not always available, a reconciler must provide a solution for this condition. For example, the reconciler might include both old and new versions of the embedded object in the reconciled version. The reconciler must not attempt to reconcile across links.

The initiator stores the document versions being merged. In many cases, the initiator has access to the storage of each version and saves the result of reconciliation using similar storage. Sometimes, however, the initiator might have an in-memory object for which no persistent version is available. This situation can occur when a document containing open embedded objects must be reconciled before being saved. In such cases, the initiator saves the result of the reconciliation in the version found in memory.

The initiator uses the [IPersistStorage](https://msdn.microsoft.com/library/ms679731(VS.85).aspx) interface to bind (load) the merged version. The initiator uses the [IPersistStorage::Load](https://msdn.microsoft.com/library/ms680557(VS.85).aspx) method if an initial version has already been created and uses the [IPersistStorage::InitNew](https://msdn.microsoft.com/library/ms687194(VS.85).aspx) method for the initial version. When the merged version is loaded, the initiator uses [QueryInterface](https://msdn.microsoft.com/library/ms682521(VS.85).aspx) to retrieve the address of the [**IReconcilableObject**](https://msdn.microsoft.com/en-us/library/Bb761351(v=VS.85).aspx) interface. This interface gives the initiator access to the storage of the existing residues and gives it a way to create storage for any new residues. Then the initiator directs the interface to carry out the reconciliation. The initiator actually queries for the [IPersistFile](https://msdn.microsoft.com/library/ms687223(VS.85).aspx) interface before IPersistStorage. If the reconciler supports IPersistFile, the initiator manipulates the replica through the IPersistFile rather than the IPersistStorage methods. This permits reconciliation of files that are not stored as compound documents.

When the reconciliation is complete, the initiator can save the merged version by using the [IPersistStorage](https://msdn.microsoft.com/library/ms679731(VS.85).aspx) or [IPersistFile](https://msdn.microsoft.com/library/ms687223(VS.85).aspx) interface. During reconciliation, the briefcase reconciler creates residues as needed and writes their persistent bits to storage. If the merged version is a stream, the [IStorage](https://msdn.microsoft.com/library/Aa380015(VS.85).aspx) interface passed to [IPersistStorage::Load](https://msdn.microsoft.com/library/ms680557(VS.85).aspx) contains a stream named "Contents" with its storage state set to STATEBITS\_FLAT. (You can set the state bits by using the [IStorage::Stat](https://msdn.microsoft.com/library/Aa380033(VS.85).aspx) method.) After the merge, the initiator saves the merged version by writing the data in an appropriate manner. It should ensure that STATEBITS\_FLAT is set as appropriate for the storage.

### Residues

The initiator indicates whether it wants residues by setting the *pstgNewResidues* parameter to a valid address when calling the [**IReconcilableObject::Reconcile**](https://msdn.microsoft.com/en-us/library/Bb761353(v=VS.85).aspx) method. If the reconciler does not support the creation of residues, it must return immediately the REC\_E\_NORESIDUES value, unless the *dwFlags* parameter specifies the **RECONCILEF\_NORESIDUESOK** value.

The briefcase reconciler returns residues to the initiator by creating new storage elements and copying them to the array pointed to by *pstgNewResidues*. For structured storage residues, the reconciler copies an [IStorage](https://msdn.microsoft.com/library/Aa380015(VS.85).aspx) interface, and for flat storage residues, it copies either an [IStream](https://msdn.microsoft.com/library/Aa380034(VS.85).aspx) or an IStorage interface with the STATEBITS\_FLAT flag set. The reconciler uses IStorage to create the necessary storage, using [IStorage::CreateStream](https://msdn.microsoft.com/library/Aa380020(VS.85).aspx) to create flat storage for a residue that is a stream and [IStorage::CreateStorage](https://msdn.microsoft.com/library/Aa380019(VS.85).aspx) to create structured storage.

The initiator prepares *pstgNewResidues* so that it contains no elements in the nonreserved part of the [IStorage](https://msdn.microsoft.com/library/Aa380015(VS.85).aspx) namespace. The briefcase reconciler places each residue in an element whose name corresponds to the order of its initial version. For example, the first residue is contained in "1", the second in "2", and so on. If the reconciled object itself produces a residue, it is found in the element named "0".

The briefcase reconciler commits each of the newly created elements individually, ensuring that the initiator has access to the information. The reconciler does not, however, commit *pstgNewResidues* itself. The initiator is responsible for committing this or otherwise disposing of it.

## Briefcase Reconciler Reference

This section contains information about the reconciliation interfaces. When handling errors, a method can return only those error values that are explicitly defined as possible return values. Furthermore, the method must set all variables whose addresses are passed as parameters to **NULL** before returning from the error.

### Briefcase Reconciler Interfaces and Methods

-   [**IReconcilableObject**](https://msdn.microsoft.com/en-us/library/Bb761351(v=VS.85).aspx) 
    -   -   [**IReconcilableObject::GetProgressFeedbackMaxEstimate**](https://msdn.microsoft.com/en-us/library/Bb761349(v=VS.85).aspx)
        -   [**IReconcilableObject::Reconcile**](https://msdn.microsoft.com/en-us/library/Bb761353(v=VS.85).aspx)

-   [**IReconcileInitiator**](ireconcileinitiator.md) 
    -   -   [**IReconcileInitiator::SetAbortCallback**](https://msdn.microsoft.com/en-us/library/Bb761345(v=VS.85).aspx)
        -   [**IReconcileInitiator::SetProgressFeedback**](https://msdn.microsoft.com/en-us/library/Bb761347(v=VS.85).aspx)

-   [**INotifyReplica**](https://docs.microsoft.com/windows/desktop/api/reconcil/nn-reconcil-inotifyreplica) 
    -   -   [**INotifyReplica::YouAreAReplica**](https://docs.microsoft.com/windows/desktop/api/reconcil/nf-reconcil-inotifyreplica-youareareplica)

 

 




