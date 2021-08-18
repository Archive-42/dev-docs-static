# Element: msContentZoom event

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `msContentZoom` event fires when a user zooms the element (changes the scale of the content).

It is a proprietary event specific to Microsoft Edge and Internet Explorer.

Zoomed elements can expose their zoom level through `msContentZoom` (ie. scrollTop/Left). The zoom level can be reset with [`Element.msZoomTo()`](mszoomto).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Unknown</td></tr><tr class="even"><td>Cancelable</td><td>Unknown</td></tr><tr class="odd"><td>Interface</td><td>Unknown</td></tr><tr class="even"><td>Event handler property</td><td>Unknown</td></tr></tbody></table>

## Example

      contentZoom.addEventListener("MSContentZoom", function(e) {
         zoomFactor.value = contentZoom.msContentZoomFactor.toFixed(2);
      });

## Specifications

Not part of any specification.

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

`msContentZoom_event`

No

12-79

No

Yes

No

No

No

No

No

No

No

No

## See also

- [CSS Style Declaration](../cssstyledeclaration)
- [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/msContentZoom_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/msContentZoom_event</a>
