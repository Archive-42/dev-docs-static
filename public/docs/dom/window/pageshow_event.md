Window: pageshow event
======================

The `pageshow` event is sent to a [`Window`](../window) when the browser displays the window's document due to navigation. This includes:

-   Initially loading the page
-   Navigating to the page from another page in the same window or tab
-   Restoring a frozen page on mobile OSes
-   Returning to the page using the browser's forward or back buttons

During the initial page load, the `pageshow` event fires *after* the [`load`](load_event) event.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../pagetransitionevent"><code>PageTransitionEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>onpageshow</code></span></td></tr></tbody></table>

Examples
--------

This example sets up event handlers for events listed in the array `events`. The handler, `eventLogger()`, logs the type of event that occurred to the console, and includes the value of the [`persisted`](../pagetransitionevent/persisted) flag on `pageshow` and `pagehide` events.

### JavaScript

    const events = [
      "pagehide", "pageshow",
      "unload", "load"
    ];

    const eventLogger = event => {
      switch (event.type) {
        case "pagehide":
        case "pageshow":
          let isPersisted = event.persisted ? "persisted" : "not persisted";
          console.log('Event:', event.type, '-', isPersisted);
          break;
        default:
          console.log('Event:', event.type);
          break;
      }
    };

    events.forEach(eventName =>
      window.addEventListener(eventName, eventLogger)
    );

### HTML

    <p>Open the console and watch the output as you navigate to and from
    this page. Try loading new pages into this tab, then navigating forward
    and backward through history, noting the events’ output to the log.</p>

### Results

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsing-the-web.html#event-pageshow">HTML Living Standard<br />
<span class="small">The definition of 'pageshow' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial specification.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#event-pageshow">HTML5<br />
<span class="small">The definition of 'pageshow' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`pageshow_event`

3

12

Yes

Yes

Yes

Yes

≤37

18

Yes

Yes

Yes

1.0

See also
--------

-   [`pagehide`](pagehide_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/pageshow_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/pageshow_event</a>
