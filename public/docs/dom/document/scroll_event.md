# Document: scroll event

The `scroll` event fires when the document view has been scrolled. For element scrolling, see [`Element: scroll event`](../element/scroll_event).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onscroll"><code>onscroll</code></a></td></tr></tbody></table>

**Note:** In iOS UIWebViews, `scroll` events are not fired while scrolling is taking place; they are only fired after the scrolling has completed. See [Bootstrap issue \#16202](https://github.com/twbs/bootstrap/issues/16202). Safari and WKWebViews are not affected by this bug.

## Examples

### Scroll event throttling

Since `scroll` events can fire at a high rate, the event handler shouldn't execute computationally expensive operations such as DOM modifications. Instead, it is recommended to throttle the event using [`requestAnimationFrame()`](../window/requestanimationframe), [`setTimeout()`](../windoworworkerglobalscope/settimeout), or a [`CustomEvent`](../customevent), as follows.

Note, however, that input events and animation frames are fired at about the same rate, and therefore the optimization below is often unnecessary. This example optimizes the`scroll` event for `requestAnimationFrame`.

    // Reference: http://www.html5rocks.com/en/tutorials/speed/animations/

    let lastKnownScrollPosition = 0;
    let ticking = false;

    function doSomething(scrollPos) {
      // Do something with the scroll position
    }

    document.addEventListener('scroll', function(e) {
      lastKnownScrollPosition = window.scrollY;

      if (!ticking) {
        window.requestAnimationFrame(function() {
          doSomething(lastKnownScrollPosition);
          ticking = false;
        });

        ticking = true;
      }
    });

See more, similar examples on the `resize` event page.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#scrolling-events">CSS Object Model (CSSOM) View Module</a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`scroll_event`

1

12

6

9

11.6

2

1

18

6

12

1

1.0

## See also

- [Element: `scroll` event](../element/scroll_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/scroll_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/scroll_event</a>
