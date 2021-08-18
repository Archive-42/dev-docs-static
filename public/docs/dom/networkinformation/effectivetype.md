# NetworkInformation.effectiveType

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `effectiveType` read-only property of the [`NetworkInformation`](../networkinformation) interface returns the effective type of the connection meaning one of 'slow-2g', '2g', '3g', or '4g'. This value is determined using a combination of recently observed, round-trip time and downlink values.

## Syntax

    var effectiveType = NetworkInformation.effectiveType

### Value

A [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) containing one of 'slow-2g', '2g', '3g', or '4g'.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/netinfo/#dom-networkinformation-effectivetype">Network Information API<br />
<span class="small">The definition of 'effectiveType' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`effectiveType`

61

79

No

No

48

No

50

38

Yes

45

No

3.0

## See also

- [Effective Connection Type](https://developer.mozilla.org/en-US/docs/Glossary/Effective_connection_type)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/effectiveType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/effectiveType</a>
