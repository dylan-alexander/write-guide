---
Description: CryptXML allows developers to extend natively supported cryptographic algorithms by registering a system wide cryptographic extension DLL.
ms.assetid: b0625481-660a-4fd5-ba15-d532998f95a6
title: XML Digital Signature Cryptographic Extensions
ms.topic: article
ms.date: 05/31/2018
---

# XML Digital Signature Cryptographic Extensions

CryptXML allows developers to extend natively supported cryptographic algorithms by registering a system wide cryptographic extension DLL. Extension DLLs extend the algorithms supported by **SignatureMethod** and **DigestMethod** XML elements. Extension DLLs can support algorithms that encode additional parameters into the XML digital signature.

All extensions DLLs must support the [**CryptXmlDllGetInterface**](https://msdn.microsoft.com/en-us/library/Dd433817(v=VS.85).aspx) function, which returns a pointer to a [**CRYPT\_XML\_CRYPTOGRAPHIC\_INTERFACE**](/windows/desktop/api/Cryptxml/ns-cryptxml-crypt_xml_cryptographic_interface) structure. This structure provides function pointers to implemented cryptographic extension functions. The functions supported depend on the type of cryptographic algorithm supported and whether the algorithm must encode parameters into the XML digital signature.

Cryptographic extensions functions include the following function pointers:

<dl> <dt>

<span id="Required_functions"></span><span id="required_functions"></span><span id="REQUIRED_FUNCTIONS"></span>Required functions
</dt> <dd>

-   [**CryptXmlDllGetInterface**](https://msdn.microsoft.com/en-us/library/Dd433817(v=VS.85).aspx)
-   [**CryptXmlDllGetAlgorithmInfo**](https://msdn.microsoft.com/en-us/library/Dd433816(v=VS.85).aspx)

</dd> <dt>

<span id="Digest_Method_functions"></span><span id="digest_method_functions"></span><span id="DIGEST_METHOD_FUNCTIONS"></span>Digest Method functions
</dt> <dd>

-   [**CryptXmlDllCloseDigest**](https://msdn.microsoft.com/en-us/library/Dd433809(v=VS.85).aspx)
-   [**CryptXmlDllCreateDigest**](https://msdn.microsoft.com/en-us/library/Dd433810(v=VS.85).aspx)
-   [**CryptXmlDllDigestData**](https://msdn.microsoft.com/en-us/library/Dd433812(v=VS.85).aspx)
-   [**CryptXmlDllFinalizeDigest**](https://msdn.microsoft.com/en-us/library/Dd433815(v=VS.85).aspx)

</dd> <dt>

<span id="Signature_Method_Functions"></span><span id="signature_method_functions"></span><span id="SIGNATURE_METHOD_FUNCTIONS"></span>Signature Method Functions
</dt> <dd>

-   [**CryptXmlDllSignData**](https://msdn.microsoft.com/en-us/library/Dd433818(v=VS.85).aspx)
-   [**CryptXmlDllVerifySignature**](https://msdn.microsoft.com/en-us/library/Dd433819(v=VS.85).aspx)
-   [**CryptXmlDllCreateKey**](https://msdn.microsoft.com/en-us/library/Dd433811(v=VS.85).aspx)
-   [**CryptXmlDllEncodeKeyValue**](https://msdn.microsoft.com/en-us/library/Dd433814(v=VS.85).aspx)

</dd> <dt>

<span id="For_algorithms_with_default_encoded_parameters"></span><span id="for_algorithms_with_default_encoded_parameters"></span><span id="FOR_ALGORITHMS_WITH_DEFAULT_ENCODED_PARAMETERS"></span>For algorithms with default encoded parameters
</dt> <dd>

-   [**CryptXmlDllEncodeAlgorithm**](https://msdn.microsoft.com/en-us/library/Dd433813(v=VS.85).aspx)

</dd> </dl>

Cryptographic extension DLLs are registered on a system-wide basis. Administrator privileges are required to register a cryptographic extension DLL.

All CryptXML cryptographic extensions are registered by the URI value set in the **SignatureMethod** or the algorithm attribute field of the **DigestMethod** element.

The registry paths for the extension DLLs are as follows:

<dl> <dt>

<span id="32-bit"></span><span id="32-BIT"></span>32-bit
</dt> <dd>

**HKEY\_LOCAL\_MACHINE**\\**SOFTWARE**\\**Microsoft**\\**Cryptography**\\**CryptXML**\\**URI**\\*{uri}*

</dd> <dt>

<span id="64-bit"></span><span id="64-BIT"></span>64-bit
</dt> <dd>

**HKEY\_LOCAL\_MACHINE**\\**SOFTWARE**\\**Microsoft**\\**Cryptography**\\**CryptXML**\\**URI**\\*{uri}*

**HKEY\_LOCAL\_MACHINE**\\**SOFTWARE**\\**WOW6432NODE**\\**Microsoft**\\**Cryptography**\\**CryptXML**\\**URI**\\*{uri}*

</dd> </dl>

Each key contains the following settings.



<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Type</th>
<th>Data</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>DLL<br/></td>
<td>Expandable string<br/></td>
<td>Required.<br/>The absolute path to the XML Cryptographic Provider DLL.
<blockquote>
<p>[!Note]We recommend that cryptographic extension DLLs be located in directories that can only be written to by applications with administrative privilege.</p>
<p><a href="https://docs.microsoft.com/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya"><strong>LoadLibrary</strong></a> is used to load the cryptographic extension DLL.<br/></p>
</blockquote>
<br/></td>
</tr>
<tr class="even">
<td>Name<br/></td>
<td><strong>String</strong></td>
<td>Optional.<br/> The display name associated with this URI.<br/></td>
</tr>
<tr class="odd">
<td>GroupId<br/></td>
<td><strong>DWORD</strong></td>
<td>Required.<br/> The group identifier associated with this cryptographic algorithm. Possible values include the following:<strong>CRYPT_XML_GROUP_ID_HASH</strong>\<strong></strong> = 1<br/><strong>CRYPT_XML_GROUP_ID_SIGN</strong>\<strong></strong> = 2<br/></td>
</tr>
<tr class="even">
<td>CNGAlgid<br/></td>
<td><strong>String</strong></td>
<td>Required.<br/> The CNG algorithm name to be passed to BCrypt or NCrypt functions.<br/></td>
</tr>
<tr class="odd">
<td>CNGExtraAlgid<br/></td>
<td><strong>String</strong></td>
<td>Optional.<br/> An extra algorithm string, other than the string in the CNGAlgid member, that can be passed to the CNG functions.<br/> For the signature algorithms (CRYPT_XML_GROUP_ID_SIGN), this member is the public key algorithm string to pass to the CNG functions.<br/> For the other values of GroupId, set the <strong>pwszCNGExtraAlgid</strong> member to the empty string, L&quot;&quot;. <br/></td>
</tr>
</tbody>
</table>



 

## Related topics

<dl> <dt>


</dt> <dt>

[XML Digital Signature Cryptographic Algorithms](xml-digital-signature-cryptographic-algorithms.md)
</dt> </dl>

 

 




