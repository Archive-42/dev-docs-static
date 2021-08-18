# NetworkInformation.type

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `NetworkInformation.type` read-only property returns the type of connection a device is using to communicate with the network.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    var type = netInfo.type

### Return value

An enumerated value that is one of the following values:

- `"bluetooth"`
- `"cellular"`
- `"ethernet"`
- `"none`"
- `"wifi"`
- `"wimax"`
- `"other"`
- `"unknown"`

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/netinfo/#dom-networkinformation-type">Network Information API<br />
<span class="small">The definition of 'type' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

61

Only supported in Chrome OS

No

No

No

No

No

50

38

31

45

No

3.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NetworkInformation/type</a>
