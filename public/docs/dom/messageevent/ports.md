MessageEvent.ports
==================

The `ports` read-only property of the [`MessageEvent`](../messageevent) interface is an array of [`MessagePort`](../messageport) objects representing the ports associated with the channel the message is being sent through (where appropriate, e.g. in channel messaging or when sending a message to a shared worker).

Syntax
------

    var myPorts = messageEvent.ports;

### Value

An array of [`MessagePort`](../messageport) objects.

Example
-------

    onconnect = function(e) {
      var port = e.ports[0];

      port.addEventListener('message', function(e) {
        var workerResult = 'Result: ' + (e.data[0] * e.data[1]);
        port.postMessage(workerResult);
      });

      port.start(); // Required when using addEventListener. Otherwise called implicitly by onmessage setter.
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-messageevent-ports">HTML Living Standard<br />
<span class="small">The definition of 'ports' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`ports`

1

12

4

9

Yes

4

1

Yes

Yes

Yes

3

Yes

See also
--------

-   [`ExtendableMessageEvent`](../extendablemessageevent) — similar to this interface but used in interfaces that needs to give more flexibility to authors.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/ports" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MessageEvent/ports</a>
