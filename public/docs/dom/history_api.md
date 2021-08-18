History API
===========

The DOM [`Window`](window) object provides access to the browser's session history (not to be confused for [WebExtensions history](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/API/history)) through the [`history`](window/history) object. It exposes useful methods and properties that let you navigate back and forth through the user's history, and manipulate the contents of the history stack.

Concepts and usage
------------------

Moving backward and forward through the user's history is done using the [`back()`](history/back), [`forward()`](history/forward), and [`go()`](history/go) methods.

### Moving forward and backward

To move backward through history:

    window.history.back()

This acts exactly as if the user clicked on the **Back** button in their browser toolbar.

Similarly, you can move forward (as if the user clicked the **Forward** button), like this:

    window.history.forward()

### Moving to a specific point in history

You can use the [`go()`](history/go) method to load a specific page from session history, identified by its relative position to the current page. (The current page's relative position is `0`.)

To move back one page (the equivalent of calling [`back()`](history/back)):

    window.history.go(-1)

To move forward a page, just like calling [`forward()`](history/forward):

    window.history.go(1)

Similarly, you can move forward 2 pages by passing `2`, and so forth.

Another use for the `go()` method is to refresh the current page by either passing `0`, or by invoking it without an argument:

    // The following statements
    // both have the effect of
    // refreshing the page
    window.history.go(0)
    window.history.go()

You can determine the number of pages in the history stack by looking at the value of the `length` property:

    let numberOfEntries = window.history.length

Interfaces
----------

[`History`](history)  
Allows manipulation of the browser *session history* (that is, the pages visited in the tab or frame that the current page is loaded in).

Examples
--------

The following example assigns a listener to the `onpopstate` property. And then illustrates some of the methods of the history object to add, replace, and move within the browser history for the current tab.

    window.onpopstate = function(event) {
      alert(`location: ${document.location}, state: ${JSON.stringify(event.state)}`)
    }

    history.pushState({page: 1}, "title 1", "?page=1")
    history.pushState({page: 2}, "title 2", "?page=2")
    history.replaceState({page: 3}, "title 3", "?page=3")
    history.back() // alerts "location: http://example.com/example.html?page=1, state: {"page":1}"
    history.back() // alerts "location: http://example.com/example.html, state: null"
    history.go(2)  // alerts "location: http://example.com/example.html?page=3, state: {"page":3}"

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#history">HTML Living Standard<br />
<span class="small">The definition of 'History' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#history">HTML5<br />
<span class="small">The definition of 'History' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`History_API`

1

12

1

10

3

1

1

18

4

10.1

1

1.0

`back`

1

12

1

10

≤12.1

1

1

18

4

≤12.1

1

1.0

`forward`

1

12

1

10

≤12.1

1

1

18

4

≤12.1

1

1.0

`go`

1

12

1

10

≤12.1

1

1

18

4

≤12.1

1

1.0

`length`

1

12

1

10

≤12.1

1

1

18

4

≤12.1

1

1.0

`pushState`

5

12

4

Until Firefox 5, the passed object is serialized using JSON. Starting in Firefox 6, the object is serialized using [the structured clone algorithm](https://developer.mozilla.org/docs/DOM/The_structured_clone_algorithm). This allows a wider variety of objects to be safely passed.

10

11.5

5

≤37

18

4

Until Firefox 5, the passed object is serialized using JSON. Starting in Firefox 6, the object is serialized using [the structured clone algorithm](https://developer.mozilla.org/docs/DOM/The_structured_clone_algorithm). This allows a wider variety of objects to be safely passed.

11.5

4

1.0

`replaceState`

5

12

4

Until Firefox 5, the passed object is serialized using JSON. Starting in Firefox 6, the object is serialized using [the structured clone algorithm](https://developer.mozilla.org/docs/DOM/The_structured_clone_algorithm). This allows a wider variety of objects to be safely passed.

10

11.5

5

≤37

18

4

Until Firefox 5, the passed object is serialized using JSON. Starting in Firefox 6, the object is serialized using [the structured clone algorithm](https://developer.mozilla.org/docs/DOM/The_structured_clone_algorithm). This allows a wider variety of objects to be safely passed.

11.5

4

1.0

`scrollRestoration`

46

79

46

No

33

11

46

46

46

33

11

5.0

`state`

19

12

4

10

≤12.1

6

≤37

25

4

≤12.1

6

1.5

See also
--------

### References

-   [`window.history`](window/history)
-   [`WindowEventHandlers.onpopstate`](windoweventhandlers/onpopstate)

### Guides

-   [Working with the History API](history_api/working_with_the_history_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/History_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/History_API</a>
