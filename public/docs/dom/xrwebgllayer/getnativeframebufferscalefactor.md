XRWebGLLayer.getNativeFramebufferScaleFactor() static method
============================================================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The static method `XRWebGLLayer.getNativeFramebufferScaleFactor()` returns a floating-point scaling factor by which one can multiply the specified [`XRSession`](../xrsession)'s resolution to get the native resolution of the WebXR device's frame buffer.

This information can be used when creating a new `XRWebGLLayer` to configure the [`XRWebGLLayerInit`](../xrwebgllayerinit) property [`framebufferScaleFactor`](../xrwebgllayerinit/framebufferscalefactor) in the options specified when calling the `XRWebGLLayer()` constructor. See the [Usage notes](#usage_notes) and [Examples](#examples) for details.

If the scaling factor is 1.0, then the frame buffer pixels and the native display pixels are the same size. If the scaling factor is greater than zero, then the frame buffer is smaller than the diplay's native dimensions, resulting in the output being up-scaled for display to the screen after rendering into the frame buffer. If the scaling factor is less than zero, the frame buffer is *larger* than the native resolution of the display, resulting in the frame buffer's contents being scaled down for display to the XR device. This can happen for display environments which use superscaling or anti-aliasing techniques to improve perceived image quality.

Syntax
------

    let nativeScaling = XRWebGLLayer.getNativeFramebufferScaleFactor(session);

### Parameters

`session`  
The [`XRSession`](../xrsession) for which to return the native framebuffer scaling factor.

### Return value

A floating-point value which, when multiplied by the [`XRSession`](../xrsession)'s recommended framebuffer dimensions, results in the XR device's native frame buffer resolution. If the session has ended, this function returns 0.0.

Usage notes
-----------

The scaling factor returned by this function will be 1.0 if the native resolution of the XR device and the resolution of the XR device match. In any case, multiplying the recommended resolution as identified by the `XRSession` by this value will result in the actual native resolution of the XR hardware.

The recommended WebGL frame buffer resolution is the best possible estimate of the resolution necessary to contain all of fthe [`XRView`](../xrview)s needed by the device while at the same time providing typical applications an acceptable balance of image quality and performance.

For example, consider a device which uses a 2560x1440 pixel frame buffer (which is used to render two views, for the left and right eyes, side by side each at a resolution of 1280x1440 pixels). Consider a frame buffer which at full size looks like this:

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjIzMy40IDEwNCA3NTAuNiA1MDQiIHdpZHRoPSI3NTAuNiIgaGVpZ2h0PSI1MDQiPjxkZWZzPjxtYXJrZXIgb3JpZW50PSJhdXRvIiBvdmVyZmxvdz0idmlzaWJsZSIgbWFya2VyVW5pdHM9InN0cm9rZVdpZHRoIiBpZD0iYSIgc3Ryb2tlLWxpbmVqb2luPSJtaXRlciIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiB2aWV3Qm94PSItMSAtNCA3IDgiIG1hcmtlcldpZHRoPSI3IiBtYXJrZXJIZWlnaHQ9IjgiIGNvbG9yPSIjMDAwIj48cGF0aCBkPSJNMCAwaDQuOG0wIDN2LTZNMCAxLjIgNC4yIDAgMC0xLjIiIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIi8+PC9tYXJrZXI+PG1hcmtlciBvcmllbnQ9ImF1dG8iIG92ZXJmbG93PSJ2aXNpYmxlIiBtYXJrZXJVbml0cz0ic3Ryb2tlV2lkdGgiIGlkPSJiIiBzdHJva2UtbGluZWpvaW49Im1pdGVyIiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIHZpZXdCb3g9Ii02IC00IDcgOCIgbWFya2VyV2lkdGg9IjciIG1hcmtlckhlaWdodD0iOCIgY29sb3I9IiMwMDAiPjxwYXRoIGQ9Ik0wIDBoLTQuOG0wLTN2Nk0wLTEuMi00LjIgMCAwIDEuMiIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJjdXJyZW50Q29sb3IiLz48L21hcmtlcj48L2RlZnM+PGcgZmlsbD0ibm9uZSI+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTIzMy40IDEwNEg5ODR2NTA0SDIzMy40eiIvPjxwYXRoIGZpbGw9IiM2NjYiIGQ9Ik0yNTYgMTkyaDMyMHYzNjBIMjU2eiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNMjU2IDE5MmgzMjB2MzYwSDI1NnoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgyNjEgNTA2KSIgZmlsbD0iI2ZmZmZkMSI+CiAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iVmVyZGFuYSIgZm9udC1zaXplPSIyOCIgZm9udC13ZWlnaHQ9IjcwMCIgeD0iOTEuNzMzIiB5PSIyOCI+TGVmdCBFeWU8L3RzcGFuPgogICAgICAgICAgPC90ZXh0PjxwYXRoIGZpbGw9IiM2NjYiIGQ9Ik01NzYgMTkyaDMyMHYzNjBINTc2eiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNNTc2IDE5MmgzMjB2MzYwSDU3NnoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg1ODEgNTA2KSIgZmlsbD0iI2ZmZmZkMSI+CiAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iVmVyZGFuYSIgZm9udC1zaXplPSIyOCIgZm9udC13ZWlnaHQ9IjcwMCIgeD0iODAuMzY1IiB5PSIyOCI+UmlnaHQgRXllPC90c3Bhbj4KICAgICAgICAgIDwvdGV4dD48cGF0aCBkPSJtNTc2IDU2MC04IDE2SDI2NGwtOC0xNiIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIvPjxwYXRoIGZpbGw9IiNmZmYiIGQ9Ik0zODUuNDA2IDU2MGg2MS4xODh2MzJoLTYxLjE4OHoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgzOTAuNDA2IDU2NSkiIGZpbGw9IiMwMDAiPgogICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJWZXJkYW5hIiBmb250LXNpemU9IjE4IiBmb250LXdlaWdodD0iNzAwIiB4PSIwIiB5PSIxOCI+MTI4MDwvdHNwYW4+CiAgICAgICAgPC90ZXh0PjxwYXRoIGQ9Im04OTYgNTYwLTggMTZINTg0bC04LTE2IiBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIi8+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTcwNS40MDYgNTYwaDYxLjE4OHYzMmgtNjEuMTg4eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDcxMC40MDYgNTY1KSIgZmlsbD0iIzAwMCI+CiAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IlZlcmRhbmEiIGZvbnQtc2l6ZT0iMTgiIGZvbnQtd2VpZ2h0PSI3MDAiIHg9IjAiIHk9IjE4Ij4xMjgwPC90c3Bhbj4KICAgICAgICA8L3RleHQ+PHBhdGggc3Ryb2tlPSIjZWJlYmViIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS13aWR0aD0iMyIgZD0iTTU3NiAxOTJ2MzYwIi8+PHBhdGggbWFya2VyLWVuZD0idXJsKCNhKSIgbWFya2VyLXN0YXJ0PSJ1cmwoI2IpIiBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIiBkPSJNMjY1LjYgMTYwaDYyMC44Ii8+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTUzOS43MTEgMTQzaDY2Ljg3NXYzNGgtNjYuODc1eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDU0NC43MSAxNDgpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJWZXJkYW5hIiBmb250LXNpemU9IjIwIiBmb250LXdlaWdodD0iNzAwIiB4PSIwIiB5PSIyMCI+MjU2MDwvdHNwYW4+CiAgICAgICAgICA8L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNDk5LjIgMTI1KSIgZmlsbD0iIzAwMCI+CiAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iRmlyYSBNb25vIGZvciBQb3dlcmxpbmUiIGZvbnQtc2l6ZT0iMTYiIGZvbnQtd2VpZ2h0PSI0MDAiIHg9IjAiIHk9IjE1Ij5mcmFtZWJ1ZmZlcldpZHRoPC90c3Bhbj4KICAgICAgICAgIDwvdGV4dD48cGF0aCBtYXJrZXItZW5kPSJ1cmwoI2EpIiBtYXJrZXItc3RhcnQ9InVybCgjYikiIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2Utd2lkdGg9IjIiIGQ9Ik05MjggMjAxLjZ2MzMyLjgiLz48cGF0aCBmaWxsPSIjZmZmIiBkPSJNOTExIDMzNC41NjNoMzR2NjYuODc1aC0zNHoiLz48dGV4dCB0cmFuc2Zvcm09InJvdGF0ZSg5MCAzMDAuMjE5IDYzOS43ODEpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJWZXJkYW5hIiBmb250LXNpemU9IjIwIiBmb250LXdlaWdodD0iNzAwIiB4PSIwIiB5PSIyMCI+MTQ0MDwvdHNwYW4+CiAgICAgICAgICA8L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJyb3RhdGUoOTAgMzM4LjMgNjI0LjcpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJGaXJhIE1vbm8gZm9yIFBvd2VybGluZSIgZm9udC1zaXplPSIxNiIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMCIgeT0iMTUiPmZyYW1lYnVmZmVySGVpZ2h0PC90c3Bhbj4KICAgICAgICAgIDwvdGV4dD48L2c+PC9zdmc+" alt="Diagram showing how a framebuffer is divided between two eyes&#39; viewpoints" width="751" height="504" />

If, on this device, it's determined that due to GPU limitations the browser needs to reduce image quality in order to improve performance to an acceptable level, it might choose to halve the resolution. In this case, the value returned by `XRWebGLLayer.getNativeFramebufferScaleFactor()` will be 2.0. This method of dividing the frame buffer between views is shown in the following diagram.

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9Ijk2OS40IDEwNCA3NTAuNiA1MDQiIHdpZHRoPSI3NTAuNiIgaGVpZ2h0PSI1MDQiPjxkZWZzPjxtYXJrZXIgb3JpZW50PSJhdXRvIiBvdmVyZmxvdz0idmlzaWJsZSIgbWFya2VyVW5pdHM9InN0cm9rZVdpZHRoIiBpZD0iYSIgc3Ryb2tlLWxpbmVqb2luPSJtaXRlciIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiB2aWV3Qm94PSItMSAtNCA3IDgiIG1hcmtlcldpZHRoPSI3IiBtYXJrZXJIZWlnaHQ9IjgiIGNvbG9yPSIjMDAwIj48cGF0aCBkPSJNMCAwaDQuOG0wIDN2LTZNMCAxLjIgNC4yIDAgMC0xLjIiIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIi8+PC9tYXJrZXI+PG1hcmtlciBvcmllbnQ9ImF1dG8iIG92ZXJmbG93PSJ2aXNpYmxlIiBtYXJrZXJVbml0cz0ic3Ryb2tlV2lkdGgiIGlkPSJiIiBzdHJva2UtbGluZWpvaW49Im1pdGVyIiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIHZpZXdCb3g9Ii02IC00IDcgOCIgbWFya2VyV2lkdGg9IjciIG1hcmtlckhlaWdodD0iOCIgY29sb3I9IiMwMDAiPjxwYXRoIGQ9Ik0wIDBoLTQuOG0wLTN2Nk0wLTEuMi00LjIgMCAwIDEuMiIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJjdXJyZW50Q29sb3IiLz48L21hcmtlcj48L2RlZnM+PGcgZmlsbD0ibm9uZSI+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTk2OS40IDEwNEgxNzIwdjUwNEg5NjkuNHoiLz48cGF0aCBmaWxsPSIjNjY2IiBkPSJNOTkyIDE5MmgzMjB2MzYwSDk5MnoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTk5MiAxOTJoMzIwdjM2MEg5OTJ6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTk3IDUwNikiIGZpbGw9IiNmZmZmZDEiPgogICAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iVmVyZGFuYSIgZm9udC1zaXplPSIyOCIgZm9udC13ZWlnaHQ9IjcwMCIgeD0iOTEuNzMzIiB5PSIyOCI+TGVmdCBFeWU8L3RzcGFuPgogICAgICAgICAgICA8L3RleHQ+PHBhdGggZmlsbD0iIzY2NiIgZD0iTTEzMTIgMTkyaDMyMHYzNjBoLTMyMHoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTEzMTIgMTkyaDMyMHYzNjBoLTMyMHoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMzE3IDUwNikiIGZpbGw9IiNmZmZmZDEiPgogICAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iVmVyZGFuYSIgZm9udC1zaXplPSIyOCIgZm9udC13ZWlnaHQ9IjcwMCIgeD0iODAuMzY1IiB5PSIyOCI+UmlnaHQgRXllPC90c3Bhbj4KICAgICAgICAgICAgPC90ZXh0PjxwYXRoIGQ9Im0xMzEyIDU2MC04IDE2aC0zMDRsLTgtMTYiIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2Utd2lkdGg9IjIiLz48cGF0aCBmaWxsPSIjZmZmIiBkPSJNMTEyNy44MDUgNTYwaDQ4LjM5MXYzMmgtNDguMzkxeiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDExMzIuODA1IDU2NSkiIGZpbGw9IiMwMDAiPgogICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IlZlcmRhbmEiIGZvbnQtc2l6ZT0iMTgiIGZvbnQtd2VpZ2h0PSI3MDAiIHg9IjAiIHk9IjE4Ij42NDA8L3RzcGFuPgogICAgICAgICAgPC90ZXh0PjxwYXRoIGQ9Im0xNjMyIDU2MC04IDE2aC0zMDRsLTgtMTYiIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2Utd2lkdGg9IjIiLz48cGF0aCBmaWxsPSIjZmZmIiBkPSJNMTQ0Ny44MDUgNTYwaDQ4LjM5MXYzMmgtNDguMzkxeiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDE0NTIuODA1IDU2NSkiIGZpbGw9IiMwMDAiPgogICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IlZlcmRhbmEiIGZvbnQtc2l6ZT0iMTgiIGZvbnQtd2VpZ2h0PSI3MDAiIHg9IjAiIHk9IjE4Ij42NDA8L3RzcGFuPgogICAgICAgICAgPC90ZXh0PjxwYXRoIHN0cm9rZT0iI2ViZWJlYiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2Utd2lkdGg9IjMiIGQ9Ik0xMzEyIDE5MnYzNjAiLz48cGF0aCBtYXJrZXItZW5kPSJ1cmwoI2EpIiBtYXJrZXItc3RhcnQ9InVybCgjYikiIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2Utd2lkdGg9IjIiIGQ9Ik0xMDAxLjYgMTYwaDYyMC44Ii8+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTEyNzUuNzExIDE0M2g2Ni44NzV2MzRoLTY2Ljg3NXoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjgwLjcxMSAxNDgpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IlZlcmRhbmEiIGZvbnQtc2l6ZT0iMjAiIGZvbnQtd2VpZ2h0PSI3MDAiIHg9IjAiIHk9IjIwIj4xMjgwPC90c3Bhbj4KICAgICAgICAgICAgPC90ZXh0Pjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDEyMzUuMiAxMjUpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IkZpcmEgTW9ubyBmb3IgUG93ZXJsaW5lIiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNDAwIiB4PSIwIiB5PSIxNSI+ZnJhbWVidWZmZXJXaWR0aDwvdHNwYW4+CiAgICAgICAgICAgIDwvdGV4dD48cGF0aCBtYXJrZXItZW5kPSJ1cmwoI2EpIiBtYXJrZXItc3RhcnQ9InVybCgjYikiIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2Utd2lkdGg9IjIiIGQ9Ik0xNjY0IDIwMS42djMzMi44Ii8+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTE2NDcgMzQxLjY3MmgzNHY1Mi42NTZoLTM0eiIvPjx0ZXh0IHRyYW5zZm9ybT0icm90YXRlKDkwIDY2NC42NjQgMTAxMS4zMzYpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IlZlcmRhbmEiIGZvbnQtc2l6ZT0iMjAiIGZvbnQtd2VpZ2h0PSI3MDAiIHg9IjAiIHk9IjIwIj43MjA8L3RzcGFuPgogICAgICAgICAgICA8L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJyb3RhdGUoOTAgNzA2LjMgOTkyLjcpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IkZpcmEgTW9ubyBmb3IgUG93ZXJsaW5lIiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNDAwIiB4PSIwIiB5PSIxNSI+ZnJhbWVidWZmZXJIZWlnaHQ8L3RzcGFuPgogICAgICAgICAgICA8L3RleHQ+PC9nPjwvc3ZnPg==" alt="Diagram showing frame buffer as scalled to half resolution" width="751" height="504" />

Now the width and height of the frame buffer are 50% what they were before, resulting in a total frame buffer size of 1280 by 720 pixels, with each eye's half of the buffer being 640x720 pixels. Now we can see the coordinates of each of the viewports representing these two views:

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9Ijk2OS40IDY0OCA3NTAuNiA1MDQiIHdpZHRoPSI3NTAuNiIgaGVpZ2h0PSI1MDQiPjxkZWZzPjxtYXJrZXIgb3JpZW50PSJhdXRvIiBvdmVyZmxvdz0idmlzaWJsZSIgbWFya2VyVW5pdHM9InN0cm9rZVdpZHRoIiBpZD0iYSIgc3Ryb2tlLWxpbmVqb2luPSJtaXRlciIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiB2aWV3Qm94PSItMSAtNCA3IDgiIG1hcmtlcldpZHRoPSI3IiBtYXJrZXJIZWlnaHQ9IjgiIGNvbG9yPSIjMDAwIj48cGF0aCBkPSJNMCAwaDQuOG0wIDN2LTZNMCAxLjIgNC4yIDAgMC0xLjIiIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIi8+PC9tYXJrZXI+PG1hcmtlciBvcmllbnQ9ImF1dG8iIG92ZXJmbG93PSJ2aXNpYmxlIiBtYXJrZXJVbml0cz0ic3Ryb2tlV2lkdGgiIGlkPSJiIiBzdHJva2UtbGluZWpvaW49Im1pdGVyIiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIHZpZXdCb3g9Ii02IC00IDcgOCIgbWFya2VyV2lkdGg9IjciIG1hcmtlckhlaWdodD0iOCIgY29sb3I9IiMwMDAiPjxwYXRoIGQ9Ik0wIDBoLTQuOG0wLTN2Nk0wLTEuMi00LjIgMCAwIDEuMiIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJjdXJyZW50Q29sb3IiLz48L21hcmtlcj48L2RlZnM+PGcgZmlsbD0ibm9uZSI+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTk2OS40IDY0OEgxNzIwdjUwNEg5NjkuNHoiLz48cGF0aCBmaWxsPSIjNjY2IiBkPSJNOTkyIDczNmgzMjB2MzYwSDk5MnoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTk5MiA3MzZoMzIwdjM2MEg5OTJ6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoOTk3IDg5OSkiIGZpbGw9IiNmZmZmZDEiPgogICAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iVmVyZGFuYSIgZm9udC1zaXplPSIyOCIgZm9udC13ZWlnaHQ9IjcwMCIgeD0iOTEuNzMzIiB5PSIyOCI+TGVmdCBFeWU8L3RzcGFuPgogICAgICAgICAgICA8L3RleHQ+PHBhdGggZmlsbD0iIzY2NiIgZD0iTTEzMTIgNzM2aDMyMHYzNjBoLTMyMHoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTEzMTIgNzM2aDMyMHYzNjBoLTMyMHoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMzE3IDg5OSkiIGZpbGw9IiNmZmZmZDEiPgogICAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iVmVyZGFuYSIgZm9udC1zaXplPSIyOCIgZm9udC13ZWlnaHQ9IjcwMCIgeD0iODAuMzY1IiB5PSIyOCI+UmlnaHQgRXllPC90c3Bhbj4KICAgICAgICAgICAgPC90ZXh0PjxwYXRoIHN0cm9rZT0iI2ViZWJlYiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2Utd2lkdGg9IjMiIGQ9Ik0xMzEyIDczNnYzNjAiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMDAwLjIxMiA3NDEpIiBmaWxsPSIjZWJlYmViIj4KICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJWZXJkYW5hIiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNzAwIiB4PSIwIiB5PSIxNiI+KDAsIDApPC90c3Bhbj4KICAgICAgICAgIDwvdGV4dD48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgxMjAzLjc1IDEwNjkpIiBmaWxsPSIjZWJlYmViIj4KICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJWZXJkYW5hIiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNzAwIiB4PSIwIiB5PSIxNiI+KDYzOSwgNzE5KTwvdHNwYW4+CiAgICAgICAgICA8L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTUxMi4zNzUgMTA2OSkiIGZpbGw9IiNlYmViZWIiPgogICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IlZlcmRhbmEiIGZvbnQtc2l6ZT0iMTYiIGZvbnQtd2VpZ2h0PSI3MDAiIHg9IjAiIHk9IjE2Ij4oMTI3OSwgNzE5KTwvdHNwYW4+CiAgICAgICAgICA8L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTMyNSA3NDEpIiBmaWxsPSIjZWJlYmViIj4KICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJWZXJkYW5hIiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNzAwIiB4PSIwIiB5PSIxNiI+KDY0MCwgMCk8L3RzcGFuPgogICAgICAgICAgPC90ZXh0PjxwYXRoIGQ9Im0xMzEyIDExMDQtOCAxNmgtMzA0bC04LTE2IiBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIi8+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTExMjEuNDA2IDExMDRoNjEuMTg4djMyaC02MS4xODh6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTEyNi40MDYgMTEwOSkiIGZpbGw9IiMwMDAiPgogICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IlZlcmRhbmEiIGZvbnQtc2l6ZT0iMTgiIGZvbnQtd2VpZ2h0PSI3MDAiIHg9IjAiIHk9IjE4Ij4xMjgwPC90c3Bhbj4KICAgICAgICAgIDwvdGV4dD48cGF0aCBkPSJtMTYzMiAxMTA0LTggMTZoLTMwNGwtOC0xNiIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIvPjxwYXRoIGZpbGw9IiNmZmYiIGQ9Ik0xNDQxLjQwNiAxMTA0aDYxLjE4OHYzMmgtNjEuMTg4eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDE0NDYuNDA2IDExMDkpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJWZXJkYW5hIiBmb250LXNpemU9IjE4IiBmb250LXdlaWdodD0iNzAwIiB4PSIwIiB5PSIxOCI+MTI4MDwvdHNwYW4+CiAgICAgICAgICA8L3RleHQ+PHBhdGggc3Ryb2tlPSIjZWJlYmViIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS13aWR0aD0iMyIgZD0iTTEzMTIgNzM2djM2MCIvPjxwYXRoIG1hcmtlci1lbmQ9InVybCgjYSkiIG1hcmtlci1zdGFydD0idXJsKCNiKSIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0iTTEwMDEuNiA3MDRoNjIwLjgiLz48cGF0aCBmaWxsPSIjZmZmIiBkPSJNMTI3NS43MTEgNjg3aDY2Ljg3NXYzNGgtNjYuODc1eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDEyODAuNzExIDY5MikiIGZpbGw9IiMwMDAiPgogICAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iVmVyZGFuYSIgZm9udC1zaXplPSIyMCIgZm9udC13ZWlnaHQ9IjcwMCIgeD0iMCIgeT0iMjAiPjEyODA8L3RzcGFuPgogICAgICAgICAgICA8L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoMTIzNS4yIDY2OSkiIGZpbGw9IiMwMDAiPgogICAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iRmlyYSBNb25vIGZvciBQb3dlcmxpbmUiIGZvbnQtc2l6ZT0iMTYiIGZvbnQtd2VpZ2h0PSI0MDAiIHg9IjAiIHk9IjE1Ij5mcmFtZWJ1ZmZlcldpZHRoPC90c3Bhbj4KICAgICAgICAgICAgPC90ZXh0PjxwYXRoIG1hcmtlci1lbmQ9InVybCgjYSkiIG1hcmtlci1zdGFydD0idXJsKCNiKSIgc3Ryb2tlPSIjMDAwIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS13aWR0aD0iMiIgZD0iTTE2NjQgNzQ1LjZ2MzMyLjgiLz48cGF0aCBmaWxsPSIjZmZmIiBkPSJNMTY0NyA4ODUuNjcyaDM0djUyLjY1NmgtMzR6Ii8+PHRleHQgdHJhbnNmb3JtPSJyb3RhdGUoOTAgMzkyLjY2NCAxMjgzLjMzNikiIGZpbGw9IiMwMDAiPgogICAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iVmVyZGFuYSIgZm9udC1zaXplPSIyMCIgZm9udC13ZWlnaHQ9IjcwMCIgeD0iMCIgeT0iMjAiPjcyMDwvdHNwYW4+CiAgICAgICAgICAgIDwvdGV4dD48dGV4dCB0cmFuc2Zvcm09InJvdGF0ZSg5MCA0MzQuMyAxMjY0LjcpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IkZpcmEgTW9ubyBmb3IgUG93ZXJsaW5lIiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNDAwIiB4PSIwIiB5PSIxNSI+ZnJhbWVidWZmZXJIZWlnaHQ8L3RzcGFuPgogICAgICAgICAgICA8L3RleHQ+PC9nPjwvc3ZnPg==" width="751" height="504" />

Since each eye gets half of the frame buffer, the result is that the left eye gets a 640x720 portion of the buffer with the viewport's `x` and `y` at 0, the width at 640, and the height set to 720. The right eye gets the other half of the frame buffer, with its viewport's `x` set at 639.

While [rendering a frame for this scene](../xrwebgllayer#rendering_every_view_in_a_frame), we get the viewport for the view and apply it to WebGL, then render the scene. This ensures that the scene we render will not only match the viewpoint we need to express (which is defined by the position and orientation data in the pose), but that the rendered output will be constrained within the correct portion of the frame buffer for the eye we're drawing, regardless of any scaling that is being performed.

Examples
--------

In this example, we request a frame buffer at the device's native resolution, regardless of any performance concerns:

    function requestNativeScaleWebGLLayer(gl, xrSession) {
      return gl.makeXRCompatible().then(() => {
        let scaleFactor = XRWebGLLayer.getNativeFramebufferScaleFactor(xrSession);
        let glLayer = new XRWebGLLayer(xrSession, gl, {
                        framebufferScaleFactor: scaleFactor
        });
        xrSession.updateRenderState({ baseLayer: glLayer });
      });
    };

This starts by calling the [WebGL rendering context](../webglrenderingcontext) function [`makeXRCompatible()`](../webglrenderingcontext/makexrcompatible). When the returned [`promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) resolves, we proceed by calling `XRWebGLLayer`'s `getNativeFramebufferScaleFactor()` static function to get the scale factor needed to reach the native resolution, and we then pass that into the [`WebGLLayer()`](xrwebgllayer) constructor as the value of the [`framebufferScaleFactor`](../xrwebgllayerinit/framebufferscalefactor) property in its `layerInit` dictionary, which is an [`XRWebGLLayerInit`](../xrwebgllayerinit) object.

That gets us a new [`XRWebGLLayer`](../xrwebgllayer) object representing a rendering surface we can use for the [`XRSession`](../xrsession); we set it as the rendering surface for `xrSession` by calling its [`updateRenderState()`](../xrsession/updaterenderstate) method, passing the new `glLayer` in using the [`XRRenderState`](../xrrenderstate) dictionary's [`XRRenderState.baseLayer`](../xrrenderstate/baselayer) property. The result is a rendering context that looks like the diagram below:

<img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjIzMy40IDY0OCA3NTAuNiA1MDQiIHdpZHRoPSI3NTAuNiIgaGVpZ2h0PSI1MDQiPjxkZWZzPjxtYXJrZXIgb3JpZW50PSJhdXRvIiBvdmVyZmxvdz0idmlzaWJsZSIgbWFya2VyVW5pdHM9InN0cm9rZVdpZHRoIiBpZD0iYSIgc3Ryb2tlLWxpbmVqb2luPSJtaXRlciIgc3Ryb2tlLW1pdGVybGltaXQ9IjEwIiB2aWV3Qm94PSItMSAtNCA3IDgiIG1hcmtlcldpZHRoPSI3IiBtYXJrZXJIZWlnaHQ9IjgiIGNvbG9yPSIjMDAwIj48cGF0aCBkPSJNMCAwaDQuOG0wIDN2LTZNMCAxLjIgNC4yIDAgMC0xLjIiIGZpbGw9Im5vbmUiIHN0cm9rZT0iY3VycmVudENvbG9yIi8+PC9tYXJrZXI+PG1hcmtlciBvcmllbnQ9ImF1dG8iIG92ZXJmbG93PSJ2aXNpYmxlIiBtYXJrZXJVbml0cz0ic3Ryb2tlV2lkdGgiIGlkPSJiIiBzdHJva2UtbGluZWpvaW49Im1pdGVyIiBzdHJva2UtbWl0ZXJsaW1pdD0iMTAiIHZpZXdCb3g9Ii02IC00IDcgOCIgbWFya2VyV2lkdGg9IjciIG1hcmtlckhlaWdodD0iOCIgY29sb3I9IiMwMDAiPjxwYXRoIGQ9Ik0wIDBoLTQuOG0wLTN2Nk0wLTEuMi00LjIgMCAwIDEuMiIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJjdXJyZW50Q29sb3IiLz48L21hcmtlcj48L2RlZnM+PGcgZmlsbD0ibm9uZSI+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTIzMy40IDY0OEg5ODR2NTA0SDIzMy40eiIvPjxwYXRoIGZpbGw9IiM2NjYiIGQ9Ik0yNTYgNzM2aDMyMHYzNjBIMjU2eiIvPjxwYXRoIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIiBkPSJNMjU2IDczNmgzMjB2MzYwSDI1NnoiLz48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSgyNjEgODk5KSIgZmlsbD0iI2ZmZmZkMSI+CiAgICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJWZXJkYW5hIiBmb250LXNpemU9IjI4IiBmb250LXdlaWdodD0iNzAwIiB4PSI5MS43MzMiIHk9IjI4Ij5MZWZ0IEV5ZTwvdHNwYW4+CiAgICAgICAgICAgIDwvdGV4dD48cGF0aCBmaWxsPSIjNjY2IiBkPSJNNTc2IDczNmgzMjB2MzYwSDU3NnoiLz48cGF0aCBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLWxpbmVqb2luPSJyb3VuZCIgZD0iTTU3NiA3MzZoMzIwdjM2MEg1NzZ6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNTgxIDg5OSkiIGZpbGw9IiNmZmZmZDEiPgogICAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iVmVyZGFuYSIgZm9udC1zaXplPSIyOCIgZm9udC13ZWlnaHQ9IjcwMCIgeD0iODAuMzY1IiB5PSIyOCI+UmlnaHQgRXllPC90c3Bhbj4KICAgICAgICAgICAgPC90ZXh0PjxwYXRoIHN0cm9rZT0iI2ViZWJlYiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2Utd2lkdGg9IjMiIGQ9Ik01NzYgNzM2djM2MCIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDI2NC4yMTIgNzQxKSIgZmlsbD0iI2ViZWJlYiI+CiAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iVmVyZGFuYSIgZm9udC1zaXplPSIxNiIgZm9udC13ZWlnaHQ9IjcwMCIgeD0iMCIgeT0iMTYiPigwLCAwKTwvdHNwYW4+CiAgICAgICAgICA8L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNDQ1IDEwNjkpIiBmaWxsPSIjZWJlYmViIj4KICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJWZXJkYW5hIiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNzAwIiB4PSIwIiB5PSIxNiI+KDEyNzksIDE0NDApPC90c3Bhbj4KICAgICAgICAgIDwvdGV4dD48dGV4dCB0cmFuc2Zvcm09InRyYW5zbGF0ZSg3NjUgMTA2OSkiIGZpbGw9IiNlYmViZWIiPgogICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IlZlcmRhbmEiIGZvbnQtc2l6ZT0iMTYiIGZvbnQtd2VpZ2h0PSI3MDAiIHg9IjAiIHk9IjE2Ij4oMjU2MCwgMTQ0MCk8L3RzcGFuPgogICAgICAgICAgPC90ZXh0Pjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDU4OSA3NDEpIiBmaWxsPSIjZWJlYmViIj4KICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJWZXJkYW5hIiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNzAwIiB4PSIwIiB5PSIxNiI+KDEyODAsIDApPC90c3Bhbj4KICAgICAgICAgIDwvdGV4dD48cGF0aCBkPSJtNTc2IDExMDQtOCAxNkgyNjRsLTgtMTYiIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2Utd2lkdGg9IjIiLz48cGF0aCBmaWxsPSIjZmZmIiBkPSJNMzg1LjQwNiAxMTA0aDYxLjE4OHYzMmgtNjEuMTg4eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDM5MC40MDYgMTEwOSkiIGZpbGw9IiMwMDAiPgogICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IlZlcmRhbmEiIGZvbnQtc2l6ZT0iMTgiIGZvbnQtd2VpZ2h0PSI3MDAiIHg9IjAiIHk9IjE4Ij4xMjgwPC90c3Bhbj4KICAgICAgICAgIDwvdGV4dD48cGF0aCBkPSJtODk2IDExMDQtOCAxNkg1ODRsLTgtMTYiIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2Utd2lkdGg9IjIiLz48cGF0aCBmaWxsPSIjZmZmIiBkPSJNNzA1LjQwNiAxMTA0aDYxLjE4OHYzMmgtNjEuMTg4eiIvPjx0ZXh0IHRyYW5zZm9ybT0idHJhbnNsYXRlKDcxMC40MDYgMTEwOSkiIGZpbGw9IiMwMDAiPgogICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IlZlcmRhbmEiIGZvbnQtc2l6ZT0iMTgiIGZvbnQtd2VpZ2h0PSI3MDAiIHg9IjAiIHk9IjE4Ij4xMjgwPC90c3Bhbj4KICAgICAgICAgIDwvdGV4dD48cGF0aCBzdHJva2U9IiNlYmViZWIiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIzIiBkPSJNNTc2IDczNnYzNjAiLz48cGF0aCBtYXJrZXItZW5kPSJ1cmwoI2EpIiBtYXJrZXItc3RhcnQ9InVybCgjYikiIHN0cm9rZT0iIzAwMCIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2Utd2lkdGg9IjIiIGQ9Ik0yNjUuNiA3MDRoNjIwLjgiLz48cGF0aCBmaWxsPSIjZmZmIiBkPSJNNTM5LjcxMSA2ODdoNjYuODc1djM0aC02Ni44NzV6Ii8+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNTQ0LjcxIDY5MikiIGZpbGw9IiMwMDAiPgogICAgICAgICAgICAgIDx0c3BhbiBmb250LWZhbWlseT0iVmVyZGFuYSIgZm9udC1zaXplPSIyMCIgZm9udC13ZWlnaHQ9IjcwMCIgeD0iMCIgeT0iMjAiPjI1NjA8L3RzcGFuPgogICAgICAgICAgICA8L3RleHQ+PHRleHQgdHJhbnNmb3JtPSJ0cmFuc2xhdGUoNDk5LjIgNjY5KSIgZmlsbD0iIzAwMCI+CiAgICAgICAgICAgICAgPHRzcGFuIGZvbnQtZmFtaWx5PSJGaXJhIE1vbm8gZm9yIFBvd2VybGluZSIgZm9udC1zaXplPSIxNiIgZm9udC13ZWlnaHQ9IjQwMCIgeD0iMCIgeT0iMTUiPmZyYW1lYnVmZmVyV2lkdGg8L3RzcGFuPgogICAgICAgICAgICA8L3RleHQ+PHBhdGggbWFya2VyLWVuZD0idXJsKCNhKSIgbWFya2VyLXN0YXJ0PSJ1cmwoI2IpIiBzdHJva2U9IiMwMDAiIHN0cm9rZS1saW5lY2FwPSJyb3VuZCIgc3Ryb2tlLXdpZHRoPSIyIiBkPSJNOTI4IDc0NS42djMzMi44Ii8+PHBhdGggZmlsbD0iI2ZmZiIgZD0iTTkxMSA4NzguNTYzaDM0djY2Ljg3NWgtMzR6Ii8+PHRleHQgdHJhbnNmb3JtPSJyb3RhdGUoOTAgMjguMjE5IDkxMS43ODEpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IlZlcmRhbmEiIGZvbnQtc2l6ZT0iMjAiIGZvbnQtd2VpZ2h0PSI3MDAiIHg9IjAiIHk9IjIwIj4xNDQwPC90c3Bhbj4KICAgICAgICAgICAgPC90ZXh0Pjx0ZXh0IHRyYW5zZm9ybT0icm90YXRlKDkwIDY2LjMgODk2LjcpIiBmaWxsPSIjMDAwIj4KICAgICAgICAgICAgICA8dHNwYW4gZm9udC1mYW1pbHk9IkZpcmEgTW9ubyBmb3IgUG93ZXJsaW5lIiBmb250LXNpemU9IjE2IiBmb250LXdlaWdodD0iNDAwIiB4PSIwIiB5PSIxNSI+ZnJhbWVidWZmZXJIZWlnaHQ8L3RzcGFuPgogICAgICAgICAgICA8L3RleHQ+PC9nPjwvc3ZnPg==" width="751" height="504" />

Each time the [`XRViewerPose`](../xrviewerpose)'s [`views`](../xrviewerpose/views) are iterated over for rendering, the rendering loop obtains an [`XRView`](../xrview) for the left eye which has its top-left corner at (0, 0) with its width and height being 1280x1440 pixels. The right eye it obtains has its top-left corner at 1280, 0 with the same width and height: 1280x1440.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://immersive-web.github.io/webxr/#dom-xrwebgllayer-getnativeframebufferscalefactor">WebXR Device API<br />
<span class="small">The definition of 'static XRWebGLLayer.getNativeFramebufferScaleFactor()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`getNativeFramebufferScaleFactor`

79

79

No

No

No

No

No

79

No

No

No

11.2

See also
--------

-   [WebXR Device API](../webxr_device_api)
-   [WebXR performance guide](../webxr_device_api/performance)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/getNativeFramebufferScaleFactor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XRWebGLLayer/getNativeFramebufferScaleFactor</a>