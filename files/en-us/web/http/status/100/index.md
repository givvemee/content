---
title: 100 Continue
slug: Web/HTTP/Status/100
page-type: http-status-code
spec-urls: https://www.rfc-editor.org/rfc/rfc9110#status.100
---

{{HTTPSidebar}}

The HTTP **`100 Continue`** informational status response code
indicates that everything so far is OK and that the client should continue with the
request or ignore it if it is already finished.

To have a server check the request's headers, a client must send
{{HTTPHeader("Expect")}}`: 100-continue` as a header in its initial request
and receive a `100 Continue` status code in response before sending the body.

## Status

```http
100 Continue
```

## Specifications

{{Specifications}}

## See also

- {{HTTPHeader("Expect")}}
- {{HTTPStatus(417)}}
