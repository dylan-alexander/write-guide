---
title: The OLE Component Object Model
description: The OLE Component Object Model
ms.assetid: f3200d81-c2fa-4cc7-bf85-54f6c753a529
ms.topic: article
ms.date: 05/31/2018
---

# The OLE Component Object Model

The objects used by the AVIFile library are all part of the OLE Component Object Model. Primarily, this means they share certain methods that make them easier to work with, and the values they return are common to most OLE interface methods.

The OLE Component Object Model of the file and stream handlers uses the OLE **IClassFactory** interface to create instances of their object class. As component objects, they implement the [IUnknown](iunknown.md) interface, which consists of the [**QueryInterface**](https://msdn.microsoft.com/en-us/library/Dd757101(v=VS.85).aspx), [**Release**](https://msdn.microsoft.com/en-us/library/Dd757102(v=VS.85).aspx), and [**AddRef**](https://msdn.microsoft.com/en-us/library/Dd757100(v=VS.85).aspx) methods. The **IUnknown** interface lets an application obtain pointers to other interfaces supported by the same object.

You can determine if an object supports a specific interface by using the **QueryInterface** method. If an object supports a specified interface, **QueryInterface** returns a pointer to that interface.

You can increment and decrement the reference count associated with an object by using the [**AddRef**](https://msdn.microsoft.com/en-us/library/Dd757100(v=VS.85).aspx) and [**Release**](https://msdn.microsoft.com/en-us/library/Dd757102(v=VS.85).aspx) methods. The reference count lets multiple clients access an object. When an object is used by the first application, its reference count is set to 1. Applications subsequently use the **AddRef** method to increment the count to let the object keep track of the number of times it is accessed.

When an application is done using an object, it calls the **Release** method to decrement the reference count. When the reference count is zero, the object is no longer needed and **Release** frees any resources it uses and destroys the object. Because an object uses internal resources transparent to the application, the object is responsible for freeing them. For example, a file handler might need to close open disk files and free buffer memory when released.

Most OLE interface methods return result handles that are defined by using the **HRESULT** data type. This data type is made of a severity code, contextual information, a facility code, and a status code. A return result handle that indicates success has the value zero. A nonzero value indicates failure and the status code member of the return result handle provides a basis for additional interpretation. For additional information about OLE return result handles, see the *OLE Programmer's Reference*.

 

 




