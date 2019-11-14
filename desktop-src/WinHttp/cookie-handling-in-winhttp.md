---
Description: Cookie Handling in WinHTTP
ms.assetid: ef0f0847-05f6-4477-8e48-e0bea66314ab
title: Cookie Handling in WinHTTP
ms.topic: article
ms.date: 05/31/2018
---

# Cookie Handling in WinHTTP

HTTP session data is passed between the client and server in the cookie header of the request or the response. The server sends cookies to the client in the Set-cookie header of the response and the WinHTTP API resends the server cookie to the server in the cookie header of the request. The cookie handling specifications, described in rfc 2109 (HTTP State Management Mechanism), are implemented by default in WinHTTP. Recent cookie handling specifications, described in rfc 2964, are not supported by WinHTTP.

WinHTTP obtains the cookie from the servers Set-Cookie header and stores it in a cache on a per-session basis. This cookie is resent on subsequent requests in the same WinHTTP session where the target matches the source of the cookie. The WinHTTP API regenerates the request cookie header for each leg in the request.

The follow list describes several options that WinHTTP client applications can use to handle cookies:

-   Automatic Cookie Handling - WinHTTP automatically handles cookies and the client application performs no custom cookie handling.
-   Disable Automatic Cookie Handling - Automatic cookie handling in the WinHTTP API is disabled and no cookies are sent.
-   Manually specify all Cookies – Automatic cookie handling is disabled and the client application adds or removes all cookie headers for each request in the session.
-   Manual and Automatic Cookie Handling - Combine automatic and manual cookie handling.

## Disabling Automatic Cookie Handling

To disable cookie handling, the WinHTTP client application calls the [**WinHttpSetOption**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpsetoption) function with the *dwOption* parameter set to WINHTTP\_OPTION\_DISABLE\_FEATURE, and the *lpBuffer* parameter set to WINHTTP\_DISABLE\_COOKIES. The *hInternet* parameter can be either a session handle or a request handle. When cookie handling is disabled on a request handle that has sent a previous request, the client should manually remove existing request cookie headers with the [**WinHttpAddRequestHeaders**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpaddrequestheaders) function before sending the next request. For more information, see [Removing Cookie Headers](#removing-cookie-headers).

**Note**  The client application must set all cookies on the session after automatic mode has been disabled.

## Manually Specifying All Cookies

When automatic cookie handling is disabled, the WinHTTP client application has the option to manually specify all cookies. To manually set the cookie, the application calls [**WinHttpAddRequestHeaders**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpaddrequestheaders) specifying the cookie header in the *pwszHeaders* parameter. The client application should clear all cookie headers before resending the request.

The client application should also change the cookie header when the request has been redirected. To change the cookie on redirected requests, the client specifies a callback function with [**WinHttpSetStatusCallback**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpsetstatuscallback) that responds to the redirect callback case. The callback handler should clear the cookie previously sent on the request by calling [**WinHttpAddRequestHeaders**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpaddrequestheaders). For more information about removing cookie headers, see [Removing Cookie Headers](#removing-cookie-headers).

## Manual and Automatic Cookie Handling

WinHTTP client applications can combine the WinHTTP automatic cookie handling mechanism with manual cookie handling. The application adds custom cookies to the automatically generated cookie header before sending the request with the [**WinHttpSendRequest**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpsendrequest) function. The custom cookie should be the first cookie header in the request for the WinHTTP API to properly cache the cookie. The client application should also remove cookies sent on previous requests before resending a request on the same request handle. For more information, see Removing Cookie Headers.

Cookies added to a request before the call to [**WinHttpSendRequest**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpsendrequest) are included in all WinHTTP requests sent on behalf of the next **WinHttpSendRequest** and [**WinHttpReceiveResponse**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpreceiveresponse) calls. The client application may need to clear the cookie header when the request has been redirected. To clear the cookie on redirected requests, the client specifies a callback function with [**WinHttpSetStatusCallback**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpsetstatuscallback) that responds to the redirect callback case. The callback handler should clear the cookie that was previously sent on the request by calling [**WinHttpAddRequestHeaders**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpaddrequestheaders). The callback function may not set new custom cookies on the redirect callback. The client must wait for **WinHttpReceiveResponse** to complete before adding new cookies for the next **WinHttpSendRequest** call.

## Removing Cookie Headers

The WinHTTP client application may need to clear the existing request cookie before resending a request to prevent cookies that were sent on previous requests from being sent again on the current request; for more information, see the following Note. Also be aware that Cookies do not have to be cleared before the first request is sent on the request handle. The client can clear existing cookies by calling [**WinHttpAddRequestHeaders**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpaddrequestheaders) with an empty cookie header in the *pwszHeaders* parameter and the WINHTTP\_ADDREQ\_FLAG\_REPLACE flag set in the *dwModifier* parameter. The following code example shows how to clear the cookie header on the request.

``` syntax
WinHttpAddRequestHeaders( hRequest, 
                          L"Cookie:", 
                          -1, 
                          WINHTTP_ADDREQ_FLAG_REPLACE);
```

The WinHTTP API has different cookie handling behaviors for versions of the operating system earlier than Windows XP with Service Pack 2 (SP2) and Windows Server 2003 with Service Pack 1 (SP1).

**Windows XP with SP2 and later and Windows Server 2003 with SP1 and later:  **

The WinHTTP API clears all cookies sent on previous requests for the request handle. The client can manually add new cookie headers before each call to WinHttpSendRequest. If the automatic cookie handling functionality of the WinHTTP API has not been disabled, the WinHTTP API will append the new cookie header (or add a new cookie header if the client application did not add one manually) with the cookie from the server.

**Windows XP with SP2 and Windows Server 2003 with SP1:  **

The WinHTTP API does not clear the request cookie header after [**WinHttpReceiveResponse**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpreceiveresponse) completes. Cookies sent in previous requests will be resent in subsequent calls to [**WinHttpSendRequest**](/windows/desktop/api/Winhttp/nf-winhttp-winhttpsendrequest). The WinHTTP client application should clear existing cookies headers before resending a request on the request handle.

 

 



