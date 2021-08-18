UIEvent.view
============

The `UIEvent.view` read-only property returns the <span class="page-not-created">`WindowProxy`</span> object from which the event was generated. In browsers, this is the [`Window`](../window) object the event happened in.

Syntax
------

    var view = event.view;

-   `view` is a reference to an `AbstractView` object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#interface-UIEvent">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'UIEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>From <a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html">Document Object Model (DOM) Level 2 Events Specification</a>, changed the type of <code>view</code> from <code>AbstractView</code> to <code>WindowProxy</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-UIEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'UIEvent' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`view`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/view" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/UIEvent/view</a>
