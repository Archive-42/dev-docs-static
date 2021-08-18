# GlobalEventHandlers.onpointerdown

The [`GlobalEventHandlers`](../globaleventhandlers) event handler `onpointerdown` is used to specify the event handler for the `pointerdown` event, which is fired when the pointing device is initially pressed. This event can be sent to [`Window`](../window), [`Document`](../document), and [`Element`](../element) objects.

This is functionally equivalent to the `mousedown` event when generated due to user activity with a mouse or mouse-compatible device. If the `pointerdown` event isn't canceled through a call to [`preventDefault()`](../event/preventdefault), most user agents will fire a `mousedown` event, so that sites not using pointer events will work.

You can also use [`addEventListener()`](../eventtarget/addeventlistener) to add a listener for `pointerdown` events.

## Syntax

    target.onpointerdown = downHandler;

    var downHandler = target.onpointerdown;

### Value

A [`Function`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) to handle the `pointerdown` event for the `target` [`Element`](../element), [`Document`](../document), or [`Window`](../window). It receives as input the [`PointerEvent`](../pointerevent) describing the `pointerdown` event.

## Example

This example demonstrates how to watch for and act upon `pointerdown` events using `onpointerdown`. You could also use `addEventListener()`, of course.

#### JavaScript

First, let's look at the JavaScript code that handles the `pointerdown` event.

    var targetBox = document.getElementById("target");

    targetBox.onpointerdown = handleDown;

    function handleDown(evt) {
      var action;

      switch(evt.pointerType) {
        case "mouse":
          action = "clicking";
          break;
        case "pen":
          action = "tapping";
          break;
        case "touch":
          action = "touching";
          break;
        default:
          action = "interacting with";
          break;
      }

      targetBox.textContent = `Thanks for ${action} me!`;
      evt.preventDefault();
    }

This uses `onpointerdown` to establish the function `handleDown()` as the event handler for pointer down events.

The `handleDown()` function, in turn, looks at the value of [`pointerType`](../pointerevent/pointertype) to determine what kind of pointing device was used, then uses that information to customize a string to replace the contents of the target box.

Then the event's [`preventDefault()`](../event/preventdefault) method is called to ensure that the `mousedown` event isn't triggered, potentially causing events to be handled twice if we had a handler for those events in case Pointer Event support is missing.

We also have a handler for `pointerup` events:

    targetBox.onpointerup = handleUp;

    function handleUp(evt) {
      targetBox.textContent = "Tap me, click me, or touch me!";
      evt.preventDefault();
    }

This code's job is to just restore the original text into the target box after the user's interaction with the element ends (for example, when they release the mouse button, or when they lift the stylus or finger from the screen).

In addition, the event's [`preventDefault()`](../event/preventdefault) method is called to ensure that the `mouseup` event isn't triggered unnecessarily.

#### HTML

The HTML is extremely simple:

    <div id="target">
      Tap me, click me, or touch me!
    </div>

#### CSS

The CSS sets up the appearance of the target, and doesn't affect its functionality at all.

    #target {
      width: 400px;
      height: 30px;
      text-align: center;
      font: 16px "Open Sans", "Helvetica", sans-serif;
      color: white;
      background-color: blue;
      border: 2px solid darkblue;
      cursor: pointer;
      user-select: none;
      -moz-user-select: none;
      -webkit-user-select: none;
      -ms-user-select: none;
    }

#### Result

The resulting output is shown below. Try tapping, clicking, or touching the box and see what happens. For full effect, try it with a variety of pointer types.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#dom-globaleventhandlers-onpointerdown">Pointer Events – Level 2<br />
<span class="small">The definition of 'onpointerdown' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Non-stable version</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#widl-GlobalEventHandlers-onpointerdown">Pointer Events<br />
<span class="small">The definition of 'onpointerdown' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`onpointerdown`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

## See also

- [Pointer events](../pointer_events)
- [Using Pointer Events](../pointer_events/using_pointer_events)
- [Coordinate systems](https://developer.mozilla.org/en-US/docs/Web/CSS/CSSOM_View/Coordinate_systems)
- `Document: pointerdown` event
- `HTMLElement: pointerdown` event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerdown" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onpointerdown</a>
