EventListener
=============

The `EventListener` interface represents an object that can handle an event dispatched by an [`EventTarget`](eventtarget) object.

**Note:** Due to the need for compatibility with legacy content, `EventListener` accepts both a function and an object with a `handleEvent()` property function. This is shown in the [example](#example) below.

Properties
----------

*This interface neither implements, nor inherits, any properties.*

Methods
-------

*This interface doesn't inherit any methods.*

[`EventListener.handleEvent()`](eventlistener/handleevent)  
A function that is called whenever an event of the specified type occurs.

Example
-------

### HTML

    <button id="btn">Click here!</button>

### JavaScript

    const buttonElement = document.getElementById('btn');

    // Add a handler for the 'click' event by providing a callback function.
    // Whenever the element is clicked, a pop-up with "Element clicked!" will
    // appear.
    buttonElement.addEventListener('click', function (event) {
      alert('Element clicked through function!');
    });

    // For compatibility, a non-function object with a `handleEvent` property is
    // treated just the same as a function itself.
    buttonElement.addEventListener('click', {
      handleEvent: function (event) {
        alert('Element clicked through handleEvent property!');
      }
    });

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#callbackdef-eventlistener">DOM<br />
<span class="small">The definition of 'EventListener' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-EventListener">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'EventListener' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`EventListener`

1

12

1

9

7

1

1

18

4

10.1

1

1.0

`handleEvent`

1

12

1

9

7

1

1

18

4

10.1

1

1.0

### See also

-   [addEventListener](eventtarget/addeventlistener)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventListener" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventListener</a>
