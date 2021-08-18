Element: click event
====================

An element receives a `click` event when a pointing device button (such as a mouse's primary mouse button) is both pressed and released while the pointer is located inside the element.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onclick"><code>onclick</code></a></td></tr></tbody></table>

If the button is pressed on one element and the pointer is moved outside the element before the button is released, the event is fired on the most specific ancestor element that contained both elements.

`click` fires after both the `mousedown` and `mouseup` events have fired, in that order.

Usage notes
-----------

The [`MouseEvent`](../mouseevent) object passed into the event handler for `click` has its [`detail`](../uievent/detail) property set to the number of times the [`target`](../event/target) was clicked. In other words, `detail` will be 2 for a double-click, 3 for triple-click, and so forth. This counter resets after a short interval without any clicks occurring; the specifics of how long that interval is may vary from browser to browser and across platforms. The interval is also likely to be affected by user preferences; for example, accessibility options may extend this interval to make it easier to perform multiple clicks with adaptive interfaces.

### Internet Explorer

Internet Explorer 8 & 9 suffer from a bug where elements with a computed [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) of [`transparent`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#transparent_keyword) that are overlaid on top of other element(s) won't receive `click` events. Any `click` events will be fired at the underlying element(s) instead. See [this live example](https://jsfiddle.net/YUKma/show/) for a demonstration.

Known workarounds for this bug:

-   For IE9 only:
    -   Set [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color)`: rgba(0,0,0,0)`
    -   Set [`opacity`](https://developer.mozilla.org/en-US/docs/Web/CSS/opacity)`: 0` and an explicit [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) other than [`transparent`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#transparent_keyword)
-   For IE8 and IE9: Set `filter: alpha(opacity=0);` and an explicit [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) other than [`transparent`](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#transparent_keyword)

### Safari Mobile

Safari Mobile 7.0+ (and likely earlier versions too) [suffers from a bug](https://bugs.webkit.org/show_bug.cgi?id=153887) where `click` events aren't fired on elements that aren't typically interactive (e.g. [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)) and which also don't have event listeners directly attached to the elements themselves (i.e. [event delegation](https://davidwalsh.name/event-delegate) is being used). See [this live example](https://jsfiddle.net/cvrhulu/k9t0sdnf/show/) for a demonstration. See also [Safari's docs on making elements clickable](https://developer.apple.com/library/safari/documentation/appleapplications/reference/safariwebcontent/HandlingEvents/HandlingEvents.html#//apple_ref/doc/uid/TP40006511-SW6) and the [definition of "clickable element"](https://developer.apple.com/library/safari/documentation/appleapplications/reference/safariwebcontent/HandlingEvents/HandlingEvents.html#//apple_ref/doc/uid/TP40006511-SW7).

Known workarounds for this bug:

-   Set [`cursor`](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor)`: pointer;` on the element or any of its ancestors.
-   Add a dummy `onclick="void(0)"` attribute to the element or any of its ancestors up to but not including [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body).
-   Use a typically interactive element (e.g., [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)) instead of one that isn't typically interactive (e.g., [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)).
-   Stop using `click` [event delegation](https://davidwalsh.name/event-delegate).

Safari Mobile considers the following elements to be typically interactive (and thus they aren't affected by this bug):

-   [`<a>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) (but it must have an `href`)
-   [`<area>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/area) (but it must have an `href`)
-   [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
-   [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img)
-   [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
-   [`<label>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label) (but it must be associated with a form control)
-   [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea)
-   *This list is incomplete; you can help MDN by doing further testing/research and expanding it.*

Examples
--------

This example displays the number of consecutive clicks on a [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button).

### HTML

    <button>Click</button>

### JavaScript

    const button = document.querySelector('button');

    button.addEventListener('click', event => {
      button.textContent = `Click count: ${event.detail}`;
    });

### Result

Try making rapid, repeated clicks on the button to increase the click count. If you take a break between clicks, the count will reset.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-click">UI Events</a></td><td><span class="spec-wd">Working Draft</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-click">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'click' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-eventgroupings-mouseevents-h3">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'click' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

Browser compatibility
---------------------

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

`click_event`

1

12

6

Beginning in Firefox 68, Firefox no longer incorrectly sends a `click` event for buttons other than the primary mouse button; previouly, there were circumstances in which this would occur. One example: middle-clicking a link would send a `click` to the document's `<html>` element.

9

11.6

3

1

18

6

12.1

1

1.0

`on_disabled_form_elements`

Yes

Only works for `<textarea>` elements and some `<input>` element types.

79

Only works for `<textarea>` elements and some `<input>` element types.

No

Yes

Internet Explorer only triggers the `click` event on `<input>` elements of type `checkbox` or `radio` when the element is double-clicked.

Yes

Only works for `<textarea>` elements and some `<input>` element types.

?

Yes

Only works for `<textarea>` elements and some `<input>` element types.

Yes

Only works for `<textarea>` elements and some `<input>` element types.

No

Yes

Only works for `<textarea>` elements and some `<input>` element types.

?

Yes

Only works for `<textarea>` elements and some `<input>` element types.

See also
--------

-   [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
-   `auxclick`
-   `contextmenu`
-   `dblclick`
-   `mousedown`
-   `mouseup`
-   `pointerdown`
-   `pointerup`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/click_event</a>
