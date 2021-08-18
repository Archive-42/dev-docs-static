# Document: wheel event

The `wheel` event fires when the user rotates a wheel button on a pointing device (typically a mouse).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../wheelevent"><code>WheelEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onwheel"><code>GlobalEventHandlers.onwheel</code></a></td></tr></tbody></table>

This event replaces the non-standard deprecated `mousewheel` event.

**Note:** Don't confuse the `wheel` event with the `scroll` event. The default action of a `wheel` event is implementation-specific, and doesn't necessarily dispatch a `scroll` event. Even when it does, the `delta*` values in the `wheel` event don't necessarily reflect the content's scrolling direction. Therefore, do not rely on the `wheel` event's `delta*` properties to get the scrolling direction. Instead, detect value changes of [`scrollLeft`](../element/scrollleft) and [`scrollTop`](../element/scrolltop) in the `scroll` event.

## Examples

### Scaling an element via the wheel

This example shows how to scale an element using the mouse (or other pointing device) wheel.

    <div>Scale me with your mouse wheel.</div>

    body {
      min-height: 100vh;
      margin: 0;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    div {
      width: 105px;
      height: 105px;
      background: #cdf;
      padding: 5px;
    }

    function zoom(event) {
      event.preventDefault();

      if (event.deltaY < 0) {
        // Zoom in
        scale *= event.deltaY * -2;
      }
      else {
        // Zoom out
        scale /= event.deltaY * 2;
      }

      // Restrict scale
      scale = Math.min(Math.max(.125, scale), 4);

      // Apply scale transform
      el.style.transform = `scale(${scale})`;
    }

    let scale = 1;
    const el = document.querySelector('div');
    document.onwheel = zoom;

### addEventListener equivalent

The event handler can also be set up using the `addEventListener()` method:

    document.addEventListener('wheel', zoom);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-wheel">UI Events<br />
<span class="small">The definition of 'wheel' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`wheel_event`

61

12

Yes

Yes

48

6.1

61

61

Yes

45

No

8.0

## See also

- [`WheelEvent`](../wheelevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/wheel_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/wheel_event</a>
