---
title: 'Response (k6/http)'
category: 'k6api-class'
description: 'Returned by the http.* methods that generate HTTP requests.'
---

Response is used by the http.\* methods that generate HTTP request. Those methods return one (or more, in the case of `http.batch()`) Response objects that contain HTTP response contents and performance timing measurements.

Note that in the case of redirects, all the information in the Response object will pertain to the last request (the one that doesn't get redirected).

| Name                                                                                                     | Type     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| -------------------------------------------------------------------------------------------------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Response.body`                                                                                          | string   | Response body content.<br /><br />See [Params.responseType](/javascript-api/k6-http/params-k6-http) and [options.discardResponseBodies](/using-k6/options) for how to discard the body when it's not needed (and to save memory) or when handling bodies with binary data.                                                                                                                                                                                                                                                  |
| `Response.cookies`                                                                                       | object   | Response cookies. The object properties are the cookie names and the value is an array of cookie objects (with `name`, `value`, `domain`, `path`, `httpOnly`, `secure`, `maxAge` and `expires` fields).                                                                                                                                                                                                                                                                                                                     |
| `Response.error`                                                                                         | string   | Error message if there was a non-HTTP error while trying to send the request.                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `Response.error_code`                                                                                    | number   | [Error code](/javascript-api/error-codes) if there was a non-HTTP error or 4xx or 5xx HTTP error it will be set to a specific code that describes the error. (Added in 0.24.0)                                                                                                                                                                                                                                                                                                                                              |
| `Response.headers`                                                                                       | object   | Key-value pairs representing all HTTP headers sent by the server.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `Response.ocsp.produced_at`                                                                              | number   | If a stapled OSCP response was provided by server, the number of milliseconds elapsed since 1 January 1970 00:00:00 UTC, representing the time when this OCSP stapled response was signed by CA (or by CA entrusted OCSP responder)                                                                                                                                                                                                                                                                                         |
| `Response.ocsp.this_update`                                                                              | number   | If a stapled OSCP response was provided by server, the number of milliseconds elapsed since 1 January 1970 00:00:00 UTC, representing the time at which the status being indicated was known to be correct.                                                                                                                                                                                                                                                                                                                 |
| `Response.ocsp.next_update`                                                                              | number   | If a stapled OSCP response was provided by server, the number of milliseconds elapsed since 1 January 1970 00:00:00 UTC, representing the time when this OCSP stapled response will be refreshed with CA (or by CA entrusted OCSP responder).                                                                                                                                                                                                                                                                               |
| `Response.ocsp.revocation_reason`                                                                        | string   | The reason for revocation of the certificate (if that is the status), one of the following constants: `http.OCSP_REASON_UNSPECIFIED`, `http.OCSP_REASON_KEY_COMPROMISE`, `http.OCSP_REASON_CA_COMPROMISE`, <br />`http.OCSP_REASON_AFFILIATION_CHANGED`, <br />`http.OCSP_REASON_SUPERSEDED`, <br />`http.OCSP_REASON_CESSATION_OF_OPERATION`, <br />`http.OCSP_REASON_CERTIFICATE_HOLD`, <br />`http.OCSP_REASON_REMOVE_FROM_CRL`, <br />`http.OCSP_REASON_PRIVILEGE_WITHDRAWN` or <br />`http.OCSP_REASON_AA_COMPROMISE`. |
| `Response.ocsp.revoked_at`                                                                               | number   | If a stapled OSCP response was provided by server, the number of milliseconds elapsed since 1 January 1970 00:00:00 UTC, representing the time when this certificate was revoked (if that is the status).                                                                                                                                                                                                                                                                                                                   |
| `Response.ocsp.status`                                                                                   | string   | The status of the certificate, one of the following constants: `http.OCSP_STATUS_GOOD`, `http.OCSP_STATUS_REVOKED`, `http.OCSP_STATUS_UNKNOWN` or `http.OCSP_STATUS_SERVER_FAILED`.                                                                                                                                                                                                                                                                                                                                         |
| `Response.proto`                                                                                         | string   | Protocol used to perform the transfer. Possible values are "HTTP/1.0", "HTTP/1.1", or "HTTP/2.0".                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `Response.remote_ip`                                                                                     | string   | The IP address of the server handling the request.                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `Response.remote_port`                                                                                   | number   | The port that was connected to on the server side.                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `Response.request.body`                                                                                  | string   | Request body content.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `Response.request.cookies`                                                                               | object   | Request cookies. The object properties are the cookie names and the value is an array of cookie objects (with `name`, `value` and `replace` fields).                                                                                                                                                                                                                                                                                                                                                                        |
| `Response.request.headers`                                                                               | object   | Request headers.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| `Response.request.method`                                                                                | string   | Request HTTP method.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `Response.request.url`                                                                                   | string   | Request URL.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| `Response.status`                                                                                        | number   | HTTP status code returned by server.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `Response.timings`                                                                                       | object   | Performance timing information for the HTTP request.                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| `Response.timings.blocked`                                                                               | float    | Containing time (ms) spent blocked before initiating request.                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `Response.timings.looking_up` (currently unavailable)                                                    | float    | Containing time (ms) spent looking up host name in DNS.                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `Response.timings.connecting`                                                                            | float    | Containing time (ms) spent setting up TCP connection to host.                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `Response.timings.tls_handshaking`                                                                       | float    | Containing time (ms) spent handshaking TLS session with host.                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| `Response.timings.sending`                                                                               | float    | Containing time (ms) spent sending request.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| `Response.timings.waiting`                                                                               | float    | Containing time (ms) spent waiting for server response.                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `Response.timings.receiving`                                                                             | float    | Containing time (ms) spent receiving response data.                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| `Response.timings.duration`                                                                              | float    | Total time for the request (ms). It's equal to `sending + waiting + receiving`, i.e. how long did the remote server take to process the request and respond, without the initial DNS lookup/connection times.                                                                                                                                                                                                                                                                                                               |
| `Response.tls_cipher_suite`                                                                              | string   | If a TLS session was established, the cipher suite that was used.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| `Response.tls_version`                                                                                   | string   | If a TLS session was established, the version of SSL/TLS that was used.                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `Response.url`                                                                                           | string   | The URL that was ultimately fetched (i.e. after any potential redirects).                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| `[Response.clickLink( [params] )](/javascript-api/k6-http/response-k6-http/response-clicklink-params)`   | function | Parses response as HTML, looks for a specific link and does the request-level equivalent of a click on that link.                                                                                                                                                                                                                                                                                                                                                                                                           |
| `Response.html()`                                                                                        | function | Returns an object that supports [Selection.find(selector)](/javascript-api/k6-html/selection/selection-find-selector).                                                                                                                                                                                                                                                                                                                                                                                                      |
| `Response.json([selector])`                                                                              | function | Parses the response body data as JSON and returns a JS object or array. This call caches the deserialized JSON data, additional calls will return the cached data. An optional selector can be specified to extract a specific part of the data, see [here for selector syntax](https://github.com/tidwall/gjson#path-syntax).                                                                                                                                                                                              |
| `[Response.submitForm( [params] )](/javascript-api/k6-http/response-k6-http/response-submitform-params)` | function | Parses response as HTML, parses the specified form (defaults to looking for a "form" element) with option to override fields and then submits form taking form's `method` and `action` into account.                                                                                                                                                                                                                                                                                                                        |

### Example

<div class="code-group" data-props='{"labels": []}'>

```js
import { check } from 'k6';
import http from 'k6/http';

export default function () {
  let res = http.get('https://k6.io');
  for (var p in res.headers) {
    if (res.headers.hasOwnProperty(p)) {
      console.log(p + ' : ' + res.headers[p]);
    }
  }
  check(res, {
    'status is 200': (r) => r.status === 200,
    'caption is correct': (r) => r.html('h1').text() == 'Example Domain',
  });
}
```

</div>

_A k6 script that will make an HTTP request and print all HTTP response headers_