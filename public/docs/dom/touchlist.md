TouchList
=========

The `TouchList` interface represents a list of contact points on a touch surface. For example, if the user has three fingers on the touch surface (such as a screen or trackpad), the corresponding `TouchList` object would have one [`Touch`](touch) object for each finger, for a total of three entries.

Properties
----------

 [`TouchList.length`](touchlist/length) <span class="badge inline readonly">Read only </span>   
The number of [`Touch`](touch) objects in the `TouchList`.

Methods
-------

 [`TouchList.identifiedTouch()`](touchlist/identifiedtouch) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns the first [`Touch`](touch) item in the list whose identifier matches a specified value.

[`TouchList.item()`](touchlist/item)  
Returns the [`Touch`](touch) object at the specified index in the list.

Example
-------

See the [example on the main Touch events article](touch_events#example).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#touchlist-interface">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#touchlist-interface">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`TouchList`

18

≤18

52

18-24

No

15

10.1

Yes

Yes

6

14

2

Yes

`identifiedTouch`

?

?

?

No

?

No

?

?

?

?

?

?

`item`

18

≤18

52

18-24

No

15

10.1

Yes

Yes

6

14

2

Yes

`length`

18

≤18

52

18-24

No

15

10.1

Yes

Yes

6

14

2

Yes

See also
--------

-   [Touch events](touch_events)
-   [`Document.createTouchList()`](document/createtouchlist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TouchList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TouchList</a>
