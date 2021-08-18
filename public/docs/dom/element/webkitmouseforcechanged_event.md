# Element: webkitmouseforcechanged event

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The non-standard `webkitmouseforcechanged` event is fired by Safari each time the amount of pressure changes on the trackpad/touchscreen.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Unknown</td></tr><tr class="even"><td>Cancelable</td><td>Unknown</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr></tbody></table>

`webkitmouseforcechanged` is a proprietary, WebKit-specific event introduced by Apple to support their [Force Touch events](../force_touch_events) feature.

This event first fires after the `mousedown` event and stops firing before the `mouseup` event.

## Specifications

_Not part of any specification._ Apple has [a description at the Mac Developer Library](https://developer.apple.com/library/prerelease/mac/documentation/AppleApplications/Conceptual/SafariJSProgTopics/RespondingtoForceTouchEventsfromJavaScript.html).

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

`webkitmouseforcechanged_event`

No

No

No

No

No

Yes

No

No

No

No

Yes

No

## See also

- [Force Touch events](../force_touch_events)
- `webkitmouseforcewillbegin`
- `webkitmouseforcedown`
- `webkitmouseforceup`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforcechanged_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/webkitmouseforcechanged_event</a>
