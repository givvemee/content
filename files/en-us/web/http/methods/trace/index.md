---
title: TRACE
slug: Web/HTTP/Methods/TRACE
page-type: http-method
spec-urls: https://www.rfc-editor.org/rfc/rfc9110#TRACE
---

{{HTTPSidebar}}

The **HTTP `TRACE` method** performs a message loop-back test along the path to the target resource, providing a useful debugging mechanism.

The final recipient of the request should reflect the message received, excluding any fields that might include sensitive data, back to the client as the message body of a {{HTTPStatus("200")}} (`OK`) response with a {{HTTPHeader("Content-Type")}} of `message/http`. The final recipient is either the origin server or the first server to receive a {{HTTPHeader("Max-Forwards")}} value of 0 in the request.

Note that the client must not send content in the request, or generate fields that might include sensitive data, such as stored user credentials or cookies.

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">Request has body</th>
      <td>No</td>
    </tr>
    <tr>
      <th scope="row">Successful response has body</th>
      <td>Yes</td>
    </tr>
    <tr>
      <th scope="row">{{Glossary("Safe/HTTP", "Safe")}}</th>
      <td>Yes</td>
    </tr>
    <tr>
      <th scope="row">{{Glossary("Idempotent")}}</th>
      <td>Yes</td>
    </tr>
    <tr>
      <th scope="row">{{Glossary("Cacheable")}}</th>
      <td>No</td>
    </tr>
    <tr>
      <th scope="row">Allowed in <a href="/en-US/docs/Learn/Forms">HTML forms</a></th>
      <td>No</td>
    </tr>
  </tbody>
</table>

## Syntax

```http
TRACE /index.html
```

## Specifications

{{Specifications}}

## See also

- [HTTP methods](/en-US/docs/Web/HTTP/Methods)
