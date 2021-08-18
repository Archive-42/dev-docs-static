Element: scroll event
=====================

The `scroll` event fires an element has been scrolled.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onscroll"><code>onscroll</code></a></td></tr></tbody></table>

**Note:** In iOS UIWebViews, `scroll` events are not fired while scrolling is taking place; they are only fired after the scrolling has completed. See [Bootstrap issue \#16202](https://github.com/twbs/bootstrap/issues/16202). Safari and WKWebViews are not affected by this bug.

Examples
--------

### Scroll event throttling

Since `scroll` events can fire at a high rate, the event handler shouldn't execute computationally expensive operations such as DOM modifications. Instead, it is recommended to throttle the event using [`requestAnimationFrame()`](../window/requestanimationframe), [`setTimeout()`](../windoworworkerglobalscope/settimeout), or a [`CustomEvent`](../customevent), as follows.

Note, however, that input events and animation frames are fired at about the same rate, and therefore the optimization below is often unnecessary. This example optimizes the `scroll` event for `requestAnimationFrame`.

    // Reference: http://www.html5rocks.com/en/tutorials/speed/animations/

    let last_known_scroll_position = 0;
    let ticking = false;

    function doSomething(scroll_pos) {
      // Do something with the scroll position
    }

    window.addEventListener('scroll', function(e) {
      last_known_scroll_position = window.scrollY;

      if (!ticking) {
        window.requestAnimationFrame(function() {
          doSomething(last_known_scroll_position);
          ticking = false;
        });

        ticking = true;
      }
    });

**Note**: You can find more examples on the <span class="page-not-created">`resize`</span> event page.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#scrolling-events">CSS Object Model (CSSOM) View Module</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`scroll_event`

Yes

≤18

Yes

?

?

?

Yes

Yes

Yes

?

?

Yes

See also
--------

-   Document: [`scroll`](../document/scroll_event) event

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll_event</a>
