# NetworkInformation.onchange

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `NetworkInformation.onchange` event handler contains the code that is fired when connection information changes, and the `change` is received by the [`NetworkInformation`](../networkinformation) object.

## Syntax

    netInfo.onchange = function() { ... }

## Examples

    // Get the connection type.
    var type = navigator.connection.type;

    function changeHandler(e) {
       // Handle change of connection type here.
    }

    // Register for event changes:
    navigator.connection.onchange = changeHandler;

    // Another way: navigator.connection.addEventListener('change', changeHandler);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/netinfo/#dom-networkinformation-onchange">Network Information API<br />
<span class="small">The definition of 'onchange' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`onchange`

61

79

No

No

48

No

50

38

No

On Firefox, the event handler property corresponding to the `change` event is `ontypechange`.

45

No

3.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/onchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/onchange</a>
