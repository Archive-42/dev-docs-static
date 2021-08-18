# Client.type

The `type` read-only property of the [`Client`](../client) interface indicates the type of client the service worker is controlling.

## Syntax

    var myClientType = client.type;

### Value

A string, representing the client type. The value can be one of

- `"window"`
- `"worker"`
- `"sharedworker"`

## Example

    // service worker client (e.g. a document)
    function sendMessage(message) {
      return new Promise(function(resolve, reject) {
        // note that this is the ServiceWorker.postMessage version
        navigator.serviceWorker.controller.postMessage(message);
        window.serviceWorker.onMessage = function(e) {
          resolve(e.data);
        };
      });
    }

    // controlling service worker
    self.addEventListener("message", function(e) {
      // e.source is a client object
      e.source.postMessage("Hello! Your message was: " + e.data);
      // Let's also post the type value back to the client
      e.source.postMessage(e.source.type);
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/ServiceWorker/#client-type">Service Workers<br />
<span class="small">The definition of 'type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`type`

60

17

54

No

47

11.1

60

60

54

44

11.3

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Client/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Client/type</a>
