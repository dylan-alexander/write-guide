---
Description: Encrypts a message to provide privacy.
ms.assetid: 2e09f262-9c3e-4db2-9285-017f5e1810c7
title: EncryptMessage (General) function (Sspi.h)
ms.topic: reference
ms.date: 07/25/2019
---

# EncryptMessage (General) function

The **EncryptMessage (General)** function encrypts a message to provide [*privacy*](https://docs.microsoft.com/en-us/windows/win32/secgloss/p-gly). **EncryptMessage (General)** allows an application to choose among [*cryptographic algorithms*](https://docs.microsoft.com/en-us/windows/win32/secgloss/c-gly) supported by the chosen mechanism. The **EncryptMessage (General)** function uses the [*security context*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly) referenced by the context handle. Some packages do not have messages to be encrypted or decrypted but rather provide an integrity [*hash*](https://docs.microsoft.com/en-us/windows/win32/secgloss/h-gly) that can be checked.

When using the Digest [*security support provider*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly) (SSP), this function is available as a SASL mechanism only.

When using the Schannel SSP, this function encrypts messages by using a [*session key*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly) negotiated with the remote party that will receive the message. The encryption algorithm is determined by the [[*cipher*](https://docs.microsoft.com/en-us/windows/win32/secgloss/c-gly) suite]([*cipher*](https://docs.microsoft.com/en-us/windows/win32/secgloss/c-gly)-suites-in-schannel.md) in use.

> [!Note]  
> **EncryptMessage (General)** and [**DecryptMessage (General)**](decryptmessage--general.md) can be called at the same time from two different threads in a single [*security support provider interface*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly) (SSPI) context if one thread is encrypting and the other is decrypting. If more than one thread is encrypting, or more than one thread is decrypting, each thread should obtain a unique context.

For information about using this function with a specific SSP, see the following topics.

| Topic                                                            | Description                                               |
|------------------------------------------------------------------|-----------------------------------------------------------|
| [**EncryptMessage (Digest)**](encryptmessage--digest.md)       | Encrypts a message to provide privacy by using Digest.    |
| [**EncryptMessage (Kerberos)**](encryptmessage--kerberos.md)   | Encrypts a message to provide privacy by using Kerberos.  |
| [**EncryptMessage (Negotiate)**](encryptmessage--negotiate.md) | Encrypts a message to provide privacy by using Negotiate. |
| [**EncryptMessage (NTLM)**](encryptmessage--ntlm.md)           | Encrypts a message to provide privacy by using NTLM.      |
| [**EncryptMessage (Schannel)**](encryptmessage--schannel.md)   | Encrypts a message to provide privacy by using Schannel.  |

## Syntax

```C++
);
```
## Parameters

*phContext* \[in\]

A handle to the [*security context*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly) to be used to encrypt the message.

*fQOP* \[in\]

Package-specific flags that indicate the quality of protection. A [*security package*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly) can use this parameter to enable the selection of [*cryptographic algorithms*](https://docs.microsoft.com/en-us/windows/win32/secgloss/c-gly).

When using the Digest SSP, this parameter must be set to zero.

This parameter can be one of the following flags.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Value</th><th>Meaning</th></tr></thead><tbody><tr class="odd"><td><span id="SECQOP_WRAP_NO_ENCRYPT"></span><span id="secqop_wrap_no_encrypt"></span><dl> <dt><strong>SECQOP_WRAP_NO_ENCRYPT</strong></dt> </dl></td><td>Produce a header or trailer but do not encrypt the message.<br/><blockquote>[!Note]<br />
KERB_WRAP_NO_ENCRYPT has the same value and the same meaning.</blockquote><br/></td></tr><tr class="even"><td><span id="SECQOP_WRAP_OOB_DATA"></span><span id="secqop_wrap_oob_data"></span><dl> <dt><strong>SECQOP_WRAP_OOB_DATA</strong></dt> </dl></td><td>Send an Schannel alert message. In this case, the <em>pMessage</em> parameter must contain a standard two-byte SSL/TLS event code. This value is supported only by the Schannel SSP.<br/></td></tr></tbody></table>

*pMessage* \[in, out\]

A pointer to a [**SecBufferDesc**](https://docs.microsoft.com/en-us/windows/win32/api/sspi/ns-sspi-secbufferdesc) structure. On input, the structure references one or more [**SecBuffer**](https://docs.microsoft.com/en-us/windows/win32/api/sspi/ns-sspi-secbuffer) structures. One of these can be of type SECBUFFER\_DATA. That buffer contains the message to be encrypted. The message is encrypted in place, overwriting the original contents of the structure.

The function does not process buffers with the SECBUFFER\_READONLY attribute.

The length of the [**SecBuffer**](https://docs.microsoft.com/en-us/windows/win32/api/sspi/ns-sspi-secbuffer) structure that contains the message must be no greater than **cbMaximumMessage**, which is obtained from the [**QueryContextAttributes (General)**](querycontextattributes--general.md) (SECPKG\_ATTR\_STREAM\_SIZES) function.

When using the Digest SSP, there must be a second buffer of type SECBUFFER\_PADDING or SEC\_BUFFER\_DATA to hold [*signature*](https://docs.microsoft.com/en-us/windows/win32/secgloss/d-gly#-security-digital-signature-gly) information. To get the size of the output buffer, call the [**QueryContextAttributes (General)**](querycontextattributes--general.md) function and specify SECPKG\_ATTR\_SIZES. The function will return a [**SecPkgContext\_Sizes**](https://docs.microsoft.com/en-us/windows/win32/api/sspi/ns-sspi-secpkgcontext_sizes) structure. The size of the output buffer is the sum of the values in the **cbMaxSignature** and **cbBlockSize** members.

Applications that do not use SSL must supply a [**SecBuffer**](https://docs.microsoft.com/en-us/windows/win32/api/sspi/ns-sspi-secbuffer) of type SECBUFFER\_PADDING.

*MessageSeqNo* \[in\]

The sequence number that the transport application assigned to the message. If the transport application does not maintain sequence numbers, this parameter must be zero.

When using the Digest SSP, this parameter must be set to zero. The Digest SSP manages sequence numbering internally.

When using the Schannel SSP, this parameter must be set to zero. The Schannel SSP does not use sequence numbers.

</dd> </dl>

## Return value

If the function succeeds, the function returns SEC\_E\_OK.

If the function fails, it returns one of the following error codes.

| Return code                         | Description                                                                                                                                                                 |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **SEC\_E\_BUFFER\_TOO\_SMALL**      | The output buffer is too small. For more information, see Remarks.                                                                                                          |
| **SEC\_E\_CONTEXT\_EXPIRED**        | The application is referencing a context that has already been closed. A properly written application should not receive this error.                                        |
| **SEC\_E\_CRYPTO\_SYSTEM\_INVALID** | The [*cipher*](https://docs.microsoft.com/en-us/windows/win32/secgloss/c-gly) chosen for the [*security context*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly) is not supported.                                                                       |
| **SEC\_E\_INSUFFICIENT\_MEMORY**    | There is not enough memory available to complete the requested action.                                                                                                      |
| **SEC\_E\_INVALID\_HANDLE**         | A context handle that is not valid was specified in the *phContext* parameter.                                                                                              |
| **SEC\_E\_INVALID\_TOKEN**          | No SECBUFFER\_DATA type buffer was found.                                                                                                                                   |
| **SEC\_E\_QOP\_NOT\_SUPPORTED**     | Neither confidentiality nor [*integrity*](https://docs.microsoft.com/en-us/windows/win32/secgloss/i-gly) are supported by the [*security context*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly). |

## Remarks

The **EncryptMessage (General)** function encrypts a message based on the message and the [*session key*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly) from a [*security context*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly).

If the transport application created the [*security context*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly) to support sequence detection and the caller provides a sequence number, the function includes this information with the encrypted message. Including this information protects against replay, insertion, and suppression of messages. The [*security package*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly) incorporates the sequence number passed down from the transport application.

When you use the Digest SSP, get the size of the output buffer by calling the [**QueryContextAttributes (General)**](querycontextattributes--general.md) function and specifying SECPKG\_ATTR\_SIZES. The function will return a [**SecPkgContext\_Sizes**](https://docs.microsoft.com/en-us/windows/win32/api/sspi/ns-sspi-secpkgcontext_sizes) structure. The size of the output buffer is the sum of the values in the **cbMaxSignature** and **cbBlockSize** members.

When used with the Schannel SSP, the *pMessage* parameter must contain a [**SecBufferDesc**](https://docs.microsoft.com/en-us/windows/win32/api/sspi/ns-sspi-secbufferdesc) structure with the following buffers.

> [!Note]  
> These buffers must be supplied in the order shown.

| Buffer type                | Description                                                                                 |
|----------------------------|---------------------------------------------------------------------------------------------|
| SECBUFFER\_STREAM\_HEADER  | Used internally. No initialization required.                                                |
| SECBUFFER\_DATA            | Contains the [*plaintext*](https://docs.microsoft.com/en-us/windows/win32/secgloss/s-gly) message to be encrypted. |
| SECBUFFER\_STREAM\_TRAILER | Used internally. No initialization required.                                                |
| SECBUFFER\_EMPTY           | Used internally. No initialization required. Size can be zero.                              |

When you use the Schannel SSP, determine the maximum size of each of the buffers by calling the [**QueryContextAttributes (General)**](querycontextattributes--general.md) function and specifying the SECPKG\_ATTR\_STREAM\_SIZES attribute. This function returns a [**SecPkgContext\_StreamSizes**](https://docs.microsoft.com/en-us/windows/win32/api/sspi/ns-sspi-secpkgcontext_streamsizes) structure whose members contain the maximum sizes for the header (**cbHeader** member), message (**cbMaximumMessage** member) and trailer (**cbTrailer** member) buffers.

For optimal performance, the *pMessage* structures should be allocated from contiguous memory.

**Windows XP/2000:** This function was also known as **SealMessage**. Applications should now use **EncryptMessage (General)** only.

## Requirements

|-------------------------------------|--------------------------------------------------------------------------------------------------------|
| Minimum supported client | Windows XP \[desktop apps only\]                                                            |
| Minimum supported server | Windows Server 2003 \[desktop apps only\]                                                   |
| Header                   | <dl> <dt>Sspi.h (include Security.h)</dt> </dl> |
| Library                  | <dl> <dt>Secur32.lib</dt> </dl>                 |
| DLL                      | <dl> <dt>Secur32.dll</dt> </dl>                 |

## See also

- [SSPI Functions](authentication-functions.md#sspi-functions)
- [**AcceptSecurityContext (General)**](acceptsecuritycontext--general.md)
- [**DecryptMessage (General)**](decryptmessage--general.md)
- [**InitializeSecurityContext (General)**](initializesecuritycontext--general.md)
- [**QueryContextAttributes (General)**](querycontextattributes--general.md)
- [**SecBuffer**](https://docs.microsoft.com/en-us/windows/win32/api/sspi/ns-sspi-secbuffer)
- [**SecBufferDesc**](https://docs.microsoft.com/en-us/windows/win32/api/sspi/ns-sspi-secbufferdesc)
