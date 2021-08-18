XMLHttpRequest.mozBackgroundRequest
===================================

**Draft**

This page is not complete.

**Note:** This method is not available from Web content. It requires elevated privileges to access.

`XMLHttpRequest.mozBackgroundRequest` is a Boolean, indicating if the object represents a background service request. If `true`, no load group is associated with the request, with security dialogs prevented from being shown to the user.

In cases in where a security dialog (such as authentication or a bad certificate notification) would normally be shown, this request fails instead.

**Note:** This property must be set before calling `open()`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/mozBackgroundRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/mozBackgroundRequest</a>
