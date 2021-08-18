# MouseEvent()

The `MouseEvent()` constructor creates a new [`MouseEvent`](../mouseevent).

## Syntax

     event = new MouseEvent(typeArg, mouseEventInit);

### Values

_typeArg_  
Is a [`DOMString`](../domstring) representing the name of the event.

_mouseEventInit_ <span class="badge inline optional">Optional</span>  
Is a `MouseEventInit` dictionary, having the following fields:

- `"screenX"`, optional and defaulting to `0`, of type `long`, that is the horizontal position of the mouse event on the user's screen; setting this value doesn't move the mouse pointer.
- `"screenY"`, optional and defaulting to `0`, of type `long`, that is the vertical position of the mouse event on the user's screen; setting this value doesn't move the mouse pointer.
- `"clientX"`, optional and defaulting to `0`, of type `long`, that is the horizontal position of the mouse event on the client window of user's screen; setting this value doesn't move the mouse pointer.
- `"clientY"`, optional and defaulting to `0`, of type `long`, that is the vertical position of the mouse event on the client window of the user's screen; setting this value doesn't move the mouse pointer.
- `"ctrlKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that indicates if the ctrl key was simultaneously pressed.
- `"shiftKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that indicates if the shift key was simultaneously pressed.
- `"altKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that indicates if the alt key was simultaneously pressed.
- `"metaKey"`, optional and defaulting to `false`, of type [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean), that indicates if the meta key was simultaneously pressed.
- `"button"`, optional and defaulting to `0`, of type `short`, that describes which button is pressed during events related to the press or release of a button:
  <table><thead><tr class="header"><th>Value</th><th>Meaning</th></tr></thead><tbody><tr class="odd"><td><code>0</code></td><td>Main button pressed (usually the left button) or un-initialized</td></tr><tr class="even"><td><code>1</code></td><td>Auxiliary button pressed (usually the middle button)</td></tr><tr class="odd"><td><code>2</code></td><td>Secondary button pressed (usually the right button)</td></tr></tbody></table>

- `"buttons"`, optional and defaulting to `0`, of type `unsigned short`, that describes which buttons are pressed when the event is launched:
  <table><thead><tr class="header"><th>Bit-field value</th><th>Meaning</th></tr></thead><tbody><tr class="odd"><td><code>0</code></td><td>No button pressed</td></tr><tr class="even"><td><code>1</code></td><td>Main button pressed (usually the left button)</td></tr><tr class="odd"><td><code>2</code></td><td>Secondary button pressed (usually the right button)</td></tr><tr class="even"><td><code>4</code></td><td>Auxiliary button pressed (usually the middle button)</td></tr></tbody></table>

- `"relatedTarget"`, optional and defaulting to `null`, of type [`EventTarget`](../eventtarget), that is the element just left (in case of a `mouseenter` or `mouseover`) or is entering (in case of a `mouseout` or `mouseleave`).
- `"region"`, optional and defaulting to `null`, of type [`DOMString`](../domstring), is the id of the hit region affected by the event. The absence of any hit region is affected, is represented by the `null` value.

In some implementations, passing anything other than a number for the screen and client fields will throw a `TypeError`.

_The `MouseEventInit` dictionary also accepts fields from [`UIEventInit`](../uievent/uievent) and from [`EventInit`](../event/event) dictionaries._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-mouseevent-interface">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Redefines screen and client fields long to double.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#interface-MouseEvent">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'MouseEvent()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MouseEvent`

47

≤79

11

No

Yes

Yes

47

47

14

Yes

Yes

5.0

`long_to_double`

56

≤79

?

No

?

?

56

56

?

?

?

6.0

`region_support`

51

Flag needed to retrieve value from `MouseEvent.region`.

≤79

Flag needed to retrieve value from `MouseEvent.region`.

32

No

?

?

No

No

32

?

?

No

## Polyfill

You can polyfill the `MouseEvent()` constructor functionality in Internet Explorer 9 and higher with the following code:

    (function (window) {
      try {
        new MouseEvent('test');
        return false; // No need to polyfill
      } catch (e) {
            // Need to polyfill - fall through
      }

        // Polyfills DOM4 MouseEvent
        var MouseEventPolyfill = function (eventType, params) {
            params = params || { bubbles: false, cancelable: false };
            var mouseEvent = document.createEvent('MouseEvent');
            mouseEvent.initMouseEvent(eventType,
                params.bubbles,
                params.cancelable,
                window,
                0,
                params.screenX || 0,
                params.screenY || 0,
                params.clientX || 0,
                params.clientY || 0,
                params.ctrlKey || false,
                params.altKey || false,
                params.shiftKey || false,
                params.metaKey || false,
                params.button || 0,
                params.relatedTarget || null
            );

            return mouseEvent;
        }

        MouseEventPolyfill.prototype = Event.prototype;

        window.MouseEvent = MouseEventPolyfill;
    })(window);

## See also

- [`MouseEvent`](../mouseevent), the interface of the objects it constructs.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/MouseEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/MouseEvent</a>
