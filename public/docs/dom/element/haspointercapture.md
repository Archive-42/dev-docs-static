# Element.hasPointerCapture()

The `hasPointerCapture()` method of the [`Element`](../element) interface sets whether the element on which it is invoked has pointer capture for the pointer identified by the given pointer ID.

## Syntax

    targetElement.hasPointerCapture(pointerId);

### Parameters

`pointerId`  
The [`pointerId`](../pointerevent/pointerid) of a [`PointerEvent`](../pointerevent) object.

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value — `true` if the element does have pointer capture, `false` if it doesn't.

## Examples

    <html>
      <script>
        function downHandler(ev) {
          const el = document.getElementById("target");
          // Element 'target' will receive/capture further events
          el.setPointerCapture(ev.pointerId);

          /* ... */

          // Check whether element still has pointer capture
          let pointerCap = el.hasPointerCapture(ev.pointerId);
          if(pointerCap) {
            // We've still got pointer capture
          } else {
            // oops, we've lost pointer capture!
          }
        }

        function init() {
          const el = document.getElementById("target");
          el.onpointerdown = downHandler;
        }
      </script>
      <body onload="init();">
        <div id="target">Touch this element with a pointer.</div>
      </body>
    </html>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-element-haspointercapture">Pointer Events – Level 2<br />
<span class="small">The definition of 'hasPointerCapture()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`hasPointerCapture`

55

79

59

41

No

42

13

55

55

79

41

42

13

6.0

## See also

- [`Element.setPointerCapture()`](setpointercapture)
- [`Element.releasePointerCapture()`](releasepointercapture)
- [`Pointer Events`](../pointer_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/hasPointerCapture" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/hasPointerCapture</a>
