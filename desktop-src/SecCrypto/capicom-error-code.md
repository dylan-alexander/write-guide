---
Description: Defines error codes that are returned by CAPICOM.
ms.assetid: e72b8290-b482-4629-8b87-5a15677865a6
title: CAPICOM_ERROR_CODE enumeration (Capicom.h)
ms.topic: reference
ms.date: 05/31/2018
topic_type: 
- APIRef
- kbSyntax
api_name: 
- CAPICOM_ERROR_CODE
api_type: 
- HeaderDef
api_location: 
- Capicom.h
---

# CAPICOM\_ERROR\_CODE enumeration

The **CAPICOM\_ERROR\_CODE** enumeration type defines error codes that are returned by CAPICOM.

> [!Note]  
> Visual Basic Scripting Edition errors return an **Err.number** value greater than zero. For those errors, **Err.Description** values provide information about the cause of the error. In addition to Visual Basic Scripting Edition errors, CAPICOM errors return the codes defined by **CAPICOM\_ERROR\_CODE**.

 

## Members



<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Member</th>
<th>Description</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong>CAPICOM_E_ENCODE_INVALID_TYPE</strong></td>
<td>An encoding type that is not valid was used.<br/> The following list shows the valid encoding types:
<ul>
<li>CAPICOM_ENCODE_ANY</li>
<li>CAPICOM_ENCODE_BASE64</li>
<li>CAPICOM_ENCODE_BINARY</li>
</ul>
<br/></td>
<td>0x80880100</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_EKU_INVALID_OID</strong></td>
<td>The <a href="eku-oid"><strong>OID</strong></a> property of the <a href="eku"><strong>EKU</strong></a> object cannot be set because the <a href="eku-name"><strong>Name</strong></a> property is not set to CAPICOM_EKU_OTHER.<br/> Set the <a href="eku-name"><strong>Name</strong></a> property to CAPICOM_EKU_OTHER before setting the <a href="eku-oid"><strong>OID</strong></a> property.<br/></td>
<td>0x80880200</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_EKU_OID_NOT_INITIALIZED</strong></td>
<td>The <a href="eku-oid"><strong>OID</strong></a> property of the <a href="eku"><strong>EKU</strong></a> object has not been initialized. <br/> Either set the <a href="eku-name"><strong>Name</strong></a> property to anything other than CAPICOM_EKU_OTHER, or set the <strong>Name</strong> property to CAPICOM_EKU_OTHER and the <a href="eku-oid"><strong>OID</strong></a> property to a value.<br/></td>
<td>0x80880201</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_CERTIFICATE_NOT_INITIALIZED</strong></td>
<td>The <a href="certificate"><strong>Certificate</strong></a> object has not been initialized.<br/> Usually, this error code is returned when a <a href="certificate"><strong>Certificate</strong></a> object is instantiated but not associated with a digital certificate. To associate the object with a digital certificate, either assign it to an existing <strong>Certificate</strong> object or call the <a href="certificate-import"><strong>Import</strong></a> method.<br/></td>
<td>0x80880210</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_CERTIFICATE_NO_PRIVATE_KEY</strong></td>
<td>The <a href="certificate"><strong>Certificate</strong></a> object does not have an associated private key.<br/> This error code is returned when an attempt is made to sign data using the signer's private key, but the <a href="certificate"><strong>Certificate</strong></a> object that is associated with the <a href="signer"><strong>Signer</strong></a> object cannot be used for the signing operation.<br/></td>
<td>0x80880211</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_CHAIN_NOT_BUILT</strong></td>
<td>The <a href="chain"><strong>Chain</strong></a> object has not been initialized. <br/> To initialize the <a href="chain"><strong>Chain</strong></a> object, call the <a href="chain-build"><strong>Build</strong></a> method.<br/></td>
<td>0x80880220</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_STORE_NOT_OPENED</strong></td>
<td>The <a href="store"><strong>Store</strong></a> object has not been initialized. <br/> To initialize the <a href="store"><strong>Store</strong></a> object, call the <a href="store-open"><strong>Open</strong></a> method.<br/></td>
<td>0x80880230</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_STORE_EMPTY</strong></td>
<td>The <a href="store"><strong>Store</strong></a> object does not contain any <a href="certificate"><strong>Certificate</strong></a> objects.<br/></td>
<td>0x80880231</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_STORE_INVALID_OPEN_MODE</strong></td>
<td>The <em>OpenMode</em> parameter of the <a href="store-open"><strong>Store.Open</strong></a> method does not contain a valid value of CAPICOM_STORE_OPEN_MODE.<br/> The following list shows the valid values of CAPICOM_STORE_OPEN_MODE:
<ul>
<li>CAPICOM_STORE_OPEN_READ_ONLY</li>
<li>CAPICOM_STORE_OPEN_READ_WRITE</li>
<li>CAPICOM_STORE_OPEN_MAXIMUM_ALLOWED</li>
<li>CAPICOM_STORE_OPEN_EXISTING_ONLY</li>
<li>CAPICOM_STORE_OPEN_INCLUDE_ARCHIVED</li>
</ul>
<br/></td>
<td>0x80880232</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_STORE_INVALID_SAVE_AS_TYPE</strong></td>
<td>The <em>SaveAs</em> value passed to the <a href="store-export"><strong>Export</strong></a> method of the <a href="store"><strong>Store</strong></a> object was not valid. <br/> The following list shows the valid <em>SaveAs</em> values:
<ul>
<li>CAPICOM_STORE_SAVE_AS_SERIALIZED</li>
<li>CAPICOM_STORE_SAVE_AS_PKCS7</li>
</ul>
<br/></td>
<td>0x80880233</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_ATTRIBUTE_NAME_NOT_INITIALIZED</strong></td>
<td>The <a href="attribute-name"><strong>Name</strong></a> property of the <a href="attribute"><strong>Attribute</strong></a> object has not been initialized. <br/> Set the <a href="attribute-name"><strong>Name</strong></a> property.<br/></td>
<td>0x80880240</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_ATTRIBUTE_VALUE_NOT_INITIALIZED</strong></td>
<td>The <a href="attribute-value"><strong>Value</strong></a> property of the <a href="attribute"><strong>Attribute</strong></a> object has not been initialized. <br/> Set the <a href="attribute-value"><strong>Value</strong></a> property.<br/></td>
<td>0x80880241</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_ATTRIBUTE_INVALID_NAME</strong></td>
<td>The <a href="attribute-name"><strong>Name</strong></a> property of the <a href="attribute"><strong>Attribute</strong></a> object is not valid. <br/> The following list shows the valid attribute names:
<ul>
<li>CAPICOM_AUTHENTICATED_ATTRIBUTE_SIGNING_TIME</li>
<li>CAPICOM_AUTHENTICATED_ATTRIBUTE_DOCUMENT_NAME</li>
<li>CAPICOM_AUTHENTICATED_ATTRIBUTE_DOCUMENT_DESCRIPTION</li>
</ul>
<br/></td>
<td>0x80880242</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_ATTRIBUTE_INVALID_VALUE</strong></td>
<td>The <a href="attribute-value"><strong>Value</strong></a> property of the <a href="attribute"><strong>Attribute</strong></a> object is not valid because the data type does not match the data type indicated by the <strong>Name</strong> property. <br/> For example, if the <a href="attribute-value"><strong>Name</strong></a> property is set to CAPICOM_AUTHENTICATED_ATTRIBUTE_SIGNING_TIME, the data type must be <strong>DATE</strong>.<br/></td>
<td>0x80880243</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_SIGNER_NOT_INITIALIZED</strong></td>
<td>The <a href="signer"><strong>Signer</strong></a> object has not been initialized. <br/> To initialize the <a href="signer"><strong>Signer</strong></a> object, set the <a href="signer-certificate"><strong>Certificate</strong></a> property.<br/></td>
<td>0x80880250</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_SIGNER_NOT_FOUND</strong></td>
<td>The signer cannot be found in the <a href="signeddata"><strong>SignedData</strong></a> object. <br/> Usually, this does not happen with a <a href="signeddata"><strong>SignedData</strong></a> object that was created by CAPICOM; however, if the <strong>SignedData</strong> object was created by a third-party product, the signer's certificate may not be included in the PKCS #7 structure.<br/></td>
<td>0x80880251</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_SIGNER_NO_CHAIN</strong></td>
<td>A <a href="chain"><strong>Chain</strong></a> object cannot be found in the <a href="signer"><strong>Signer</strong></a> object.<br/></td>
<td>0x80880252 // v2.0</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_SIGNER_INVALID_USAGE</strong></td>
<td>An attempt is made to use the signer in a way that is not valid.<br/></td>
<td>0x80880253 //v2.0</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_SIGN_NOT_INITIALIZED</strong></td>
<td>The <a href="signeddata"><strong>SignedData</strong></a> object has not been initialized. <br/> To initialize the <a href="signeddata"><strong>SignedData</strong></a> object, set the <a href="signeddata-content"><strong>Content</strong></a> property or call the <a href="signeddata-verify"><strong>Verify</strong></a> method.<br/></td>
<td>0x80880260</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_SIGN_INVALID_TYPE</strong></td>
<td>The <a href="signeddata"><strong>SignedData</strong></a> object contains a type that is not valid. <br/> Usually, this happens when an attempt is made to verify an enveloped message with a <a href="signeddata"><strong>SignedData</strong></a> object or vice versa.<br/></td>
<td>0x80880261</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_SIGN_NOT_SIGNED</strong></td>
<td>The <a href="signeddata"><strong>SignedData</strong></a> object has not been signed. <br/> To sign the <a href="signeddata"><strong>SignedData</strong></a> object, call the <a href="signeddata-sign"><strong>Sign</strong></a> method.<br/></td>
<td>0x80880262</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_INVALID_ALGORITHM</strong></td>
<td>The algorithm value for the <a href="algorithm-name"><strong>Name</strong></a> property of the <a href="algorithm"><strong>Algorithm</strong></a> object is not valid. <br/> The following list shows the valid algorithm values for the <a href="algorithm-name"><strong>Name</strong></a> property:
<ul>
<li>CAPICOM_ENCRYPTION_ALGORITHM_RC2</li>
<li>CAPICOM_ENCRYPTION_ALGORITHM_RC4</li>
<li>CAPICOM_ENCRYPTION_ALGORITHM_DES</li>
<li>CAPICOM_ENCRYPTION_ALGORITHM_3DES</li>
</ul>
<br/></td>
<td>0x80880270</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_INVALID_KEY_LENGTH</strong></td>
<td>The key length value for the <a href="algorithm-keylength"><strong>KeyLength</strong></a> property of the <a href="algorithm"><strong>Algorithm</strong></a> object is not valid. <br/> The following list shows the valid key length values for the <a href="algorithm-keylength"><strong>KeyLength</strong></a> property:
<ul>
<li>CAPICOM_ENCRYPTION_KEY_LENGTH_MAXIMUM</li>
<li>CAPICOM_ENCRYPTION_KEY_LENGTH_40_BITS</li>
<li>CAPICOM_ENCRYPTION_KEY_LENGTH_56_BITS</li>
<li>CAPICOM_ENCRYPTION_KEY_LENGTH_128_BITS</li>
</ul>
<br/></td>
<td>0x80880271</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_ENVELOP_NOT_INITIALIZED</strong></td>
<td>The <a href="envelopeddata"><strong>EnvelopedData</strong></a> object has not been initialized. <br/> To initialize the <a href="envelopeddata"><strong>EnvelopedData</strong></a> object, either set the <a href="envelopeddata-content"><strong>Content</strong></a> property or call the <a href="envelopeddata-decrypt"><strong>Decrypt</strong></a> method.<br/></td>
<td>0x80880280</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_ENVELOP_INVALID_TYPE</strong></td>
<td>The <a href="envelopeddata"><strong>EnvelopedData</strong></a> object contains a type that is not valid. <br/> Usually, this happens when an attempt is made to verify a signed message with an <a href="envelopeddata"><strong>EnvelopedData</strong></a> object or vice versa.<br/></td>
<td>0x80880281</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_ENVELOP_NO_RECIPIENT</strong></td>
<td>There is no recipient specified in the <a href="envelopeddata"><strong>EnvelopedData</strong></a> object when the <a href="envelopeddata-encrypt"><strong>Encrypt</strong></a> method of an <strong>EnvelopedData</strong> object is called. <br/> To add a recipient, call the <a href="recipients-add"><strong>Recipients.Add</strong></a> method.<br/></td>
<td>0x80880282</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_ENVELOP_RECIPIENT_NOT_FOUND</strong></td>
<td>The recipient cannot be found in the <a href="envelopeddata"><strong>EnvelopedData</strong></a> object. <br/> Usually, this does not happen with an <a href="envelopeddata"><strong>EnvelopedData</strong></a> object that was created by CAPICOM; however, if the <strong>EnvelopedData</strong> object was created by a third-party product, the recipient's certificate may not be included in the PKCS #7 structure.<br/></td>
<td>0x80880283</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_ENCRYPT_NOT_INITIALIZED</strong></td>
<td>The <a href="encrypteddata"><strong>EncryptedData</strong></a> object has not been initialized. <br/> To initialize the <a href="encrypteddata"><strong>EncryptedData</strong></a> object, either set the <a href="encrypteddata-content"><strong>Content</strong></a> property or call the <a href="encrypteddata-decrypt"><strong>Decrypt</strong></a> method.<br/></td>
<td>0x80880290</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_ENCRYPT_INVALID_TYPE</strong></td>
<td>The <a href="encrypteddata"><strong>EncryptedData</strong></a> object is not a valid type. <br/> Usually, this means the data is corrupted.<br/></td>
<td>0x80880291</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_ENCRYPT_NO_SECRET</strong></td>
<td>The secret of an <a href="encrypteddata"><strong>EncryptedData</strong></a> object has not been initialized. <br/> To initialize the secret of an <a href="encrypteddata"><strong>EncryptedData</strong></a> object, call the <a href="encrypteddata-setsecret"><strong>SetSecret</strong></a> method.<br/></td>
<td>0x80880292</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_PRIVATE_KEY_NOT_INITIALIZED</strong></td>
<td>The <a href="privatekey"><strong>PrivateKey</strong></a> object has not been initialized.<br/></td>
<td>0x80880300 // v2.0</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_PRIVATE_KEY_NOT_EXPORTABLE</strong></td>
<td>The <a href="privatekey"><strong>PrivateKey</strong></a> object cannot be exported.<br/></td>
<td>0x80880301 // v2.0</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_ENCODE_NOT_INITIALIZED</strong></td>
<td>The <a href="encodeddata"><strong>EncodedData</strong></a> object has not been initialized.<br/></td>
<td>0x80880320 // v2.0</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_EXTENSION_NOT_INITIALIZED</strong></td>
<td>The <a href="extension"><strong>Extension</strong></a> object has not been initialized.<br/></td>
<td>0x80880330 // v2.0</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_PROPERTY_NOT_INITIALIZED</strong></td>
<td>The <a href="extendedproperty-propid"><strong>PropID</strong></a> property of the <a href="extendedproperty"><strong>ExtendedProperty</strong></a> object has not been initialized.<br/></td>
<td>0x80880340 // v2.0</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_FIND_INVALID_TYPE</strong></td>
<td>The <em>FindType</em> parameter of the <a href="certificates-find"><strong>Certificates.Find</strong></a> method is not a value of the <a href="capicom-certificate-find-type"><strong>CAPICOM_CERTIFICATE_FIND_TYPE</strong></a> enumeration.<br/></td>
<td>0x80880350 // v2.0</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_FIND_INVALID_PREDEFINED_POLICY</strong></td>
<td>The specified predefined policy for the find operation is not valid.<br/></td>
<td>0x80880351 // v2.0</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_CODE_NOT_INITIALIZED</strong></td>
<td>The <a href="signedcode"><strong>SignedCode</strong></a> object has not been initialized.<br/></td>
<td>0x80880360 // v2.0</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_CODE_NOT_SIGNED</strong></td>
<td>The <a href="signedcode"><strong>SignedCode</strong></a> object has not been signed.<br/> To sign the <a href="signedcode"><strong>SignedCode</strong></a> object, call the <a href="signedcode-sign"><strong>Sign</strong></a> method.<br/></td>
<td>0x80880361 // v2.0</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_CODE_DESCRIPTION_NOT_INITIALIZED</strong></td>
<td>The <a href="signedcode-description"><strong>Description</strong></a> property of the <a href="signedcode"><strong>SignedCode</strong></a> object has not been initialized.<br/></td>
<td>0x80880362 // v2.0</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_CODE_DESCRIPTION_URL_NOT_INITIALIZED</strong></td>
<td>The <a href="signedcode-descriptionurl"><strong>DescriptionURL</strong></a> property of the <a href="signedcode"><strong>SignedCode</strong></a> object has not been initialized.<br/></td>
<td>0x80880363 // v2.0</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_CODE_INVALID_TIMESTAMP_URL</strong></td>
<td>The <em>URL</em> parameter of the <a href="signedcode-timestamp"><strong>SignedCode.Timestamp</strong></a> method is not valid.<br/></td>
<td>0x80880364 // v2.0</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_HASH_NO_DATA</strong></td>
<td>The <a href="hasheddata"><strong>HashedData</strong></a> object does not contain any data.<br/></td>
<td>0x80880370 // v2.0</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_INVALID_CONVERT_TYPE</strong></td>
<td>The convert type is not valid.<br/></td>
<td>0x80880380 // v2.0</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_NOT_SUPPORTED</strong></td>
<td>The requested operation is not supported in the current platform. <br/></td>
<td>0x80880900</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_UI_DISABLED</strong></td>
<td>When signing, the <a href="signer-certificate"><strong>Certificate</strong></a> property of the <a href="signer"><strong>Signer</strong></a> object has not been set, but the prompt for the user certificate has been disabled. <br/> Either enable the prompt by setting the <a href="settings-enablepromptforcertificateui"><strong>EnablePromptForCertificateUI</strong></a> property of the <a href="settings"><strong>Settings</strong></a> object, or set the <a href="signer-certificate"><strong>Certificate</strong></a> property of the <a href="signer"><strong>Signer</strong></a> object.<br/></td>
<td>0x80880901</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_CANCELLED</strong></td>
<td>The operation has been canceled by the user. <br/> This happens when the user is prompted for permission to carry out a certain operation, such as accessing the private key, and the user cancels the operation.<br/></td>
<td>0x80880902</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_NOT_ALLOWED</strong></td>
<td>The attempted operation is not allowed.<br/> For example, changing the <a href="extendedproperty-propid"><strong>PropID</strong></a> property of an <a href="extendedproperty"><strong>ExtendedProperty</strong></a> object is not allowed if the object is attached to a certificate.<br/></td>
<td>0x80880903 // v2.0</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_OUT_OF_RESOURCE</strong></td>
<td>CAPICOM has run out of a resource.<br/></td>
<td>0x80880904 // v2.0</td>
</tr>
<tr class="even">
<td><strong>CAPICOM_E_INTERNAL</strong></td>
<td>An internal error has occurred. <br/> Contact Microsoft Technical Support for assistance.<br/></td>
<td>0x80880911</td>
</tr>
<tr class="odd">
<td><strong>CAPICOM_E_UNKNOWN</strong></td>
<td>An unknown error has occurred. <br/> Collect as much information as possible, and contact your vendor.<br/></td>
<td>0x80880999</td>
</tr>
</tbody>
</table>



## Requirements



|                            |                                                                                      |
|----------------------------|--------------------------------------------------------------------------------------|
| Redistributable<br/> | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                |
| Header<br/>          | <dl> <dt>Capicom.h</dt> </dl> |



 

 




