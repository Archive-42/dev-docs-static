XMLHttpRequest.onreadystatechange
=================================

An [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that is called whenever the `readyState` attribute changes. The callback is called from the user interface thread. The `XMLHttpRequest.onreadystatechange` property contains the event handler to be called when the [`readystatechange`](../document/readystatechange_event) event is fired, that is every time the [`readyState`](readystate) property of the [`XMLHttpRequest`](../xmlhttprequest) changes.

**Warning:** This should not be used with synchronous requests and must not be used from native code.

Syntax
------

    XMLHttpRequest.onreadystatechange = callback;

### Values

-   `callback` is the function to be executed when the `readyState` changes.

Examples
--------

    const xhr = new XMLHttpRequest(),
        method = "GET",
        url = "https://developer.mozilla.org/";

    xhr.open(method, url, true);
    xhr.onreadystatechange = function () {
      // In local files, status is 0 upon success in Mozilla Firefox
      if(xhr.readyState === XMLHttpRequest.DONE) {
        var status = xhr.status;
        if (status === 0 || (status >= 200 && status < 400)) {
          // The request has been completed successfully
          console.log(xhr.responseText);
        } else {
          // Oh no! There has been an error with the request!
        }
      }
    };
    xhr.send();

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#handler-xhr-onreadystatechange">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`onreadystatechange`

1

12

1

5

9

1.2

1

18

4

10.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/onreadystatechange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/onreadystatechange</a>
