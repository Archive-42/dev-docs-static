# MouseEvent

The `MouseEvent` interface represents events that occur due to the user interacting with a pointing device (such as a mouse). Common events using this interface include `click`, `dblclick`, `mouseup`, `mousedown`.

`MouseEvent` derives from [`UIEvent`](uievent), which in turn derives from [`Event`](event). Though the [`MouseEvent.initMouseEvent()`](mouseevent/initmouseevent) method is kept for backward compatibility, creating of a `MouseEvent` object should be done using the [`MouseEvent()`](mouseevent/mouseevent) constructor.

Several more specific events are based on `MouseEvent`, including [`WheelEvent`](wheelevent) and [`DragEvent`](dragevent).

## Constructor

[`MouseEvent()`](mouseevent/mouseevent)  
Creates a `MouseEvent` object.

## Properties

_This interface also inherits properties of its parents, [`UIEvent`](uievent) and [`Event`](event)._

[`MouseEvent.altKey`](mouseevent/altkey) <span class="badge inline readonly">Read only </span>  
Returns `true` if the alt key was down when the mouse event was fired.

[`MouseEvent.button`](mouseevent/button) <span class="badge inline readonly">Read only </span>  
The button number that was pressed (if applicable) when the mouse event was fired.

[`MouseEvent.buttons`](mouseevent/buttons) <span class="badge inline readonly">Read only </span>  
The buttons being depressed (if any) when the mouse event was fired.

[`MouseEvent.clientX`](mouseevent/clientx) <span class="badge inline readonly">Read only </span>  
The X coordinate of the mouse pointer in local (DOM content) coordinates.

[`MouseEvent.clientY`](mouseevent/clienty) <span class="badge inline readonly">Read only </span>  
The Y coordinate of the mouse pointer in local (DOM content) coordinates.

[`MouseEvent.ctrlKey`](mouseevent/ctrlkey) <span class="badge inline readonly">Read only </span>  
Returns `true` if the control key was down when the mouse event was fired.

[`MouseEvent.metaKey`](mouseevent/metakey) <span class="badge inline readonly">Read only </span>  
Returns `true` if the meta key was down when the mouse event was fired.

[`MouseEvent.movementX`](mouseevent/movementx) <span class="badge inline readonly">Read only </span>  
The X coordinate of the mouse pointer relative to the position of the last `mousemove` event.

[`MouseEvent.movementY`](mouseevent/movementy) <span class="badge inline readonly">Read only </span>  
The Y coordinate of the mouse pointer relative to the position of the last `mousemove` event.

[`MouseEvent.offsetX`](mouseevent/offsetx) <span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The X coordinate of the mouse pointer relative to the position of the padding edge of the target node.

[`MouseEvent.offsetY`](mouseevent/offsety) <span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The Y coordinate of the mouse pointer relative to the position of the padding edge of the target node.

[`MouseEvent.pageX`](mouseevent/pagex) <span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The X coordinate of the mouse pointer relative to the whole document.

[`MouseEvent.pageY`](mouseevent/pagey) <span class="badge inline readonly">Read only </span><span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
The Y coordinate of the mouse pointer relative to the whole document.

[`MouseEvent.region`](mouseevent/region) <span class="badge inline readonly">Read only </span>  
Returns the id of the hit region affected by the event. If no hit region is affected, `null` is returned.

[`MouseEvent.relatedTarget`](mouseevent/relatedtarget) <span class="badge inline readonly">Read only </span>  
The secondary target for the event, if there is one.

[`MouseEvent.screenX`](mouseevent/screenx) <span class="badge inline readonly">Read only </span>  
The X coordinate of the mouse pointer in global (screen) coordinates.

[`MouseEvent.screenY`](mouseevent/screeny) <span class="badge inline readonly">Read only </span>  
The Y coordinate of the mouse pointer in global (screen) coordinates.

[`MouseEvent.shiftKey`](mouseevent/shiftkey) <span class="badge inline readonly">Read only </span>  
Returns `true` if the shift key was down when the mouse event was fired.

[`MouseEvent.which`](mouseevent/which) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>  
The button being pressed when the mouse event was fired.

<span class="page-not-created">`MouseEvent.mozPressure`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>  
The amount of pressure applied to a touch or tablet device when generating the event; this value ranges between `0.0` (minimum pressure) and `1.0` (maximum pressure). Instead of using this deprecated (and non-standard) property, you should instead use [`PointerEvent`](pointerevent) and look at its [`pressure`](pointerevent/pressure) property.

[`MouseEvent.mozInputSource`](mouseevent/mozinputsource) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>  
The type of device that generated the event (one of the `MOZ_SOURCE_*` constants listed below). This lets you, for example, determine whether a mouse event was generated by an actual mouse or by a touch event (which might affect the degree of accuracy with which you interpret the coordinates associated with the event).

[`MouseEvent.webkitForce`](mouseevent/webkitforce) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>  
The amount of pressure applied when clicking

[`MouseEvent.x`](mouseevent/x) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>  
Alias for [`MouseEvent.clientX`](mouseevent/clientx).

[`MouseEvent.y`](mouseevent/y) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>  
Alias for [`MouseEvent.clientY`](mouseevent/clienty)

## Constants

[`MouseEvent.WEBKIT_FORCE_AT_MOUSE_DOWN`](mouseevent/webkit_force_at_mouse_down) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span>  
Minimum force necessary for a normal click

[`MouseEvent.WEBKIT_FORCE_AT_FORCE_MOUSE_DOWN`](mouseevent/webkit_force_at_force_mouse_down) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span>  
Minimum force necessary for a force click

## Methods

_This interface also inherits methods of its parents, [`UIEvent`](uievent) and [`Event`](event)._

[`MouseEvent.getModifierState()`](mouseevent/getmodifierstate)  
Returns the current state of the specified modifier key. See [`KeyboardEvent.getModifierState()`](keyboardevent/getmodifierstate) for details.

[`MouseEvent.initMouseEvent()`](mouseevent/initmouseevent) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Initializes the value of a `MouseEvent` created. If the event has already being dispatched, this method does nothing.

## Example

This example demonstrates simulating a click (programmatically generating a click event) on a checkbox using DOM methods. Event state (canceled or not) is then determined with the return value of method [`EventTarget.dispatchEvent()`](eventtarget/dispatchevent).

### HTML

    <p><label><input type="checkbox" id="checkbox"> Checked</label>
    <p><button id="button">Click me</button>

### JavaScript

    function simulateClick() {
      var evt = new MouseEvent("click", {
        bubbles: true,
        cancelable: true,
        view: window
      });
      var cb = document.getElementById("checkbox"); //element to click on
      var canceled = !cb.dispatchEvent(evt);
      if(canceled) {
        // A handler called preventDefault
        alert("canceled");
      } else {
        // None of the handlers called preventDefault
        alert("not canceled");
      }
    }
    document.getElementById("button").addEventListener('click', simulateClick);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-mouseevent-interface">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Redefines <code>MouseEvent</code> from long to double. This means that a <code>PointerEvent</code> whose <code>pointerType</code> is mouse will be a double.</td></tr><tr class="even"><td><a href="https://w3c.github.io/pointerlock/#extensions-to-the-mouseevent-interface">Pointer Lock<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>From <a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/">Document Object Model (DOM) Level 3 Events Specification</a>, added <code>movementX</code> and <code>movementY</code> properties.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-mouseevent-interface">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>From <a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/">Document Object Model (DOM) Level 3 Events Specification</a>, added <code>offsetX</code> and <code>offsetY</code>, <code>pageX</code> and <code>pageY</code>, <code>x</code>, and <code>y</code> properties. Redefined screen, page, client, and coordinate (x and y) properties as <code>double</code> from <code>long</code>.</td></tr><tr class="even"><td><a href="https://w3c.github.io/uievents/#interface-mouseevent">UI Events<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#events-mouseevents">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>From <a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html">Document Object Model (DOM) Level 2 Events Specification</a>, added the <code>MouseEvent()</code> constructor, the <code>getModifierState()</code> method and the <code>buttons</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-MouseEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'MouseEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

1

12

1

9

10.6

3.1

1

18

4

11

2

1.0

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

`altKey`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`button`

1

12

1

9

10.6

3.1

1

18

4

11

2

1.0

`buttons`

43

12

Yes

Resrictions apply depending on OS.

9

Yes

11.1

No

No

Yes

Yes

11.3

No

`clientX`

1

12

1

9

10.6

3.1

1

18

4

11

2

1.0

`clientY`

Yes

12

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`ctrlKey`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`getModifierState`

47

12

Yes

?

Yes

12.1

47

47

Yes

Yes

12.2

5.0

`initMouseEvent`

Yes

12

Yes

?

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`metaKey`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`movementX`

37

22-37

13

41

1-41

No

Yes

9

6-8

37

Yes-37

37

Yes-37

41

4-41

Yes

8

6-8

3.0

Yes-3.0

`movementY`

37

22-37

13

41

1-41

No

Yes

9

6-8

37

Yes-37

37

Yes-37

41

4-41

Yes

8

6-8

3.0

Yes-3.0

`offsetX`

Yes

12

39

9

Yes

Yes

Yes

Yes

43

Yes

Yes

Yes

`offsetY`

Yes

12

39

9

Yes

Yes

Yes

Yes

43

Yes

Yes

Yes

`pageX`

45

12

Yes

9

Yes

Yes

45

45

Yes

Yes

Yes

5.0

`pageY`

45

12

Yes

9

Yes

Yes

45

45

Yes

Yes

Yes

5.0

`region`

Yes

≤79

30

No

No

No

No

No

30

No

No

No

`relatedTarget`

Yes

12

48

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`screenX`

Yes

12

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`screenY`

Yes

12

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`shiftKey`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`which`

1

12

1

On `mousemove` events, the `which` property is incorrectly always set to `1`.

9

10.6

3.1

Yes

Yes

4

On `mousemove` events, the `which` property is incorrectly always set to `1`.

11

Yes

Yes

`x`

Yes

12

53

9

Yes

Yes

Yes

Yes

53

Yes

Yes

Yes

`y`

Yes

12

53

9

Yes

Yes

Yes

Yes

53

Yes

Yes

Yes

## See also

- Its direct parent, [`UIEvent`](uievent).
- [`PointerEvent`](pointerevent): For advanced pointer events, including multi-touch

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent</a>
