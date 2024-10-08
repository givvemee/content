---
title: "WebGLRenderingContext: getAttribLocation() method"
short-title: getAttribLocation()
slug: Web/API/WebGLRenderingContext/getAttribLocation
page-type: web-api-instance-method
browser-compat: api.WebGLRenderingContext.getAttribLocation
---

{{APIRef("WebGL")}}{{AvailableInWorkers}}

The **`WebGLRenderingContext.getAttribLocation()`** method of
the [WebGL API](/en-US/docs/Web/API/WebGL_API) returns the location of an
attribute variable in a given {{domxref("WebGLProgram")}}.

## Syntax

```js-nolint
getAttribLocation(program, name)
```

### Parameters

- `program`
  - : A {{domxref("WebGLProgram")}} containing the attribute variable.
- `name`
  - : A string specifying the name of the attribute variable whose
    location to get.

### Return value

A {{domxref("WebGL_API/Types", "GLint")}} number indicating the location of the variable name if found.
Returns -1 otherwise.

## Examples

```js
gl.getAttribLocation(program, "vColor");
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("WebGLRenderingContext.getUniformLocation()")}}
