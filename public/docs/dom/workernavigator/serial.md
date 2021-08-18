WorkerNavigator.serial
======================

The `serial` read-only property of the [`WorkerNavigator`](../workernavigator) interface returns a [`Serial`](../serial) object which represents the entry point into the <span class="page-not-created">`Web Serial API`</span>.

When getting, the same instance of the [`Serial`](../serial) object will always be returned.

Syntax
------

    var serialObj = self.navigator.serial;

### Value

A [`Serial`](../serial) object.

Examples
--------

The following example uses the `getPorts()` method to initialize a list of available ports.

    self.navigator.serial.getPorts()
    .then((ports) => {
      // Initialize the list of available ports.
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/serial/#extensions-to-the-workernavigator-interface">Web Serial API<br />
<span class="small">The definition of 'Extensions to the Worker Navigator Interface' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`serial`

89

89

No

No

No

No

No

No

No

No

No

No

See also
--------

-   [Read from and write to a serial port](https://web.dev/serial/)
-   [Getting started with the web serial API](https://codelabs.developers.google.com/codelabs/web-serial#0)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/serial" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerNavigator/serial</a>
