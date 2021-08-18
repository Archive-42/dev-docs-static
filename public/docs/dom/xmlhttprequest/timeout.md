XMLHttpRequest.timeout
======================

The `XMLHttpRequest.timeout` property is an `unsigned long` representing the number of milliseconds a request can take before automatically being terminated. The default value is 0, which means there is no timeout. Timeout shouldn't be used for synchronous XMLHttpRequests requests used in a [document environment](https://developer.mozilla.org/en-US/docs/Glossary/document_environment) or it will throw an `InvalidAccessError` exception. When a timeout happens, a [timeout](timeout_event) event is fired.

**Note:** You may not use a timeout for synchronous requests with an owning window.

[Using a timeout with an asynchronous request](synchronous_and_asynchronous_requests#example_using_a_timeout)

In Internet Explorer, the timeout property may be set only after calling the [open()](open) method and before calling the [send()](send) method.

Example
-------

    var xhr = new XMLHttpRequest();
    xhr.open('GET', '/server', true);

    xhr.timeout = 2000; // time in milliseconds

    xhr.onload = function () {
      // Request finished. Do processing here.
    };

    xhr.ontimeout = function (e) {
      // XMLHttpRequest timed out. Do something here.
    };

    xhr.send(null);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/#the-timeout-attribute">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>WHATWG living standard</td></tr></tbody></table>

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

`timeout`

29

12

12

8

17

12-16

6.1

≤37

29

14

18

12-16

7

2.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/timeout</a>
