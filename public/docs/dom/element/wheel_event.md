# Element: wheel event

The `wheel` event fires when the user rotates a wheel button on a pointing device (typically a mouse).

This event replaces the non-standard deprecated [`mousewheel`](mousewheel_event) event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../wheelevent"><code>WheelEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onwheel"><code>onwheel</code></a></td></tr></tbody></table>

**Note:** Don't confuse the `wheel` event with the [`scroll`](scroll_event) event. The default action of a `wheel` event is implementation-specific, and doesn't necessarily dispatch a `scroll` event. Even when it does, the `delta*` values in the `wheel` event don't necessarily reflect the content's scrolling direction. Therefore, do not rely on the `wheel` event's `delta*` properties to get the scrolling direction. Instead, detect value changes of [`scrollLeft`](scrollleft) and [`scrollTop`](scrolltop) of the target in the `scroll` event.

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

      scale += event.deltaY * -0.01;

      // Restrict scale
      scale = Math.min(Math.max(.125, scale), 4);

      // Apply scale transform
      el.style.transform = `scale(${scale})`;
    }

    let scale = 1;
    const el = document.querySelector('div');
    el.onwheel = zoom;

### addEventListener equivalent

The event handler can also be set up using the [`addEventListener()`](../eventtarget/addeventlistener) method:

    el.addEventListener('wheel', zoom);

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

17

9

Internet Explorer only exposes the wheel event via `addEventListener`; there is no `onwheel` attribute on DOM objects. See [IE bug 782835](https://connect.microsoft.com/IE/feedback/details/782835/missing-onwheel-attribute-for-the-wheel-event-although-its-supported-via-addeventlistener).

48

7

61

61

17

45

7

8.0

## See also

- [`WheelEvent`](../wheelevent)
- [Document: `wheel` event](../document/wheel_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/wheel_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/wheel_event</a>
