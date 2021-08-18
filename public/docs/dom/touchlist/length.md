TouchList.length
================

The `length` read-only property indicates the number of items (touch points) in a given [`TouchList`](../touchlist).

Syntax
------

    var numTouches = touchList.length;

### Return value

`numTouches`  
The number of touch points in `touchList`.

Example
-------

This code example illustrates the use of the [`TouchList`](../touchlist) interface's [`item`](item) method and the [`length`](length) property.

    target = document.getElementById("target");

    target.addEventListener('touchstart', function(ev) {

      // If this touchstart event started on element target,
      // set touch to the first item in the targetTouches list;
      // otherwise set touch to the first item in the touches list
      var touch;

      if (ev.targetTouches.length >= 1)
         touch = ev.targetTouches.item(0);
      else
         touch = ev.touches.item(0);
    }, false);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/touch-events/#dom-touchlist-length">Touch Events – Level 2</a></td><td><span class="spec-draft">Draft</span></td><td>Non-stable version.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/touch-events/#widl-TouchList-length">Touch Events</a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TouchList/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TouchList/length</a>
