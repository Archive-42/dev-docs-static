# PhotoCapabilities.fillLightMode

The `fillLightMode` read-only property of the [`PhotoCapabilities`](../photocapabilities) interface returns all available fill light options of the source device. Options may include `auto`, `off`, or `flash`.

## Syntax

    const lightModes = photoCapabilities.fillLightMode

### Value

An [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of available fill light modes.

`auto`  
The device's fill light will be used automatically in low light conditions.

`off`  
No fill light will be used.

`flash`  
Always use the device's fill light.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/mediacapture-image/#dom-photocapabilities-filllightmode">MediaStream Image Capture<br />
<span class="small">The definition of 'fillLightMode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`fillLightMode`

59

≤79

?

No

46

No

59

59

?

43

No

7.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PhotoCapabilities/fillLightMode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PhotoCapabilities/fillLightMode</a>
