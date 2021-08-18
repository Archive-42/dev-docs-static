# PositionOptions.enableHighAccuracy

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `PositionOptions.enableHighAccuracy` property is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates the application would like to receive the best possible results. If `true` and if the device is able to provide a more accurate position, it will do so. Note that this can result in slower response times or increased power consumption (with a GPS chip on a mobile device for example). On the other hand, if `false` (the default value), the device can take the liberty to save resources by responding more quickly and/or using less power.

## Syntax

    positionOptions.enableHighAccuracy = booleanValue

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/geolocation-api/#dom-positionoptions-enablehighaccuracy">Geolocation API<br />
<span class="small">The definition of 'PositionOptions.enableHighAccuracy' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`enableHighAccuracy`

5

12

3.5

9

16

10-15

5

≤37

18

4

16

10.1-14

Yes

1.0

## See also

- [Using geolocation](../geolocation_api)
- The [`PositionOptions`](../positionoptions) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PositionOptions/enableHighAccuracy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PositionOptions/enableHighAccuracy</a>
