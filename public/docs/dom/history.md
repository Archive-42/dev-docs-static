# History

The `History` interface allows manipulation of the browser _session history_, that is the pages visited in the tab or frame that the current page is loaded in.

## Properties

_The `History` interface doesn't inherit any property._

[`length`](history/length) <span class="badge inline readonly">Read only </span>  
Returns an `Integer` representing the number of elements in the session history, including the currently loaded page. For example, for a page loaded in a new tab this property returns `1`.

[`scrollRestoration`](history/scrollrestoration)  
Allows web applications to explicitly set default scroll restoration behavior on history navigation. This property can be either `auto` or `manual`.

[`state`](history/state) <span class="badge inline readonly">Read only </span>  
Returns an `any` value representing the state at the top of the history stack. This is a way to look at the state without having to wait for a `popstate` event.

## Methods

_The `History`_ _interface doesn't inherit any methods._

[`back()`](history/back)  
This asynchronous method goes to the previous page in session history, the same action as when the user clicks the browser's Back button. Equivalent to `history.go(-1)`.

Calling this method to go back beyond the first page in the session history has no effect and doesn't raise an exception.

[`forward()`](history/forward)  
This asynchronous method goes to the next page in session history, the same action as when the user clicks the browser's Forward button; this is equivalent to `history.go(1)`.

Calling this method to go forward beyond the most recent page in the session history has no effect and doesn't raise an exception.

[`go()`](history/go)  
Asynchronously loads a page from the session history, identified by its relative location to the current page, for example `-1` for the previous page or `1` for the next page. If you specify an out-of-bounds value (for instance, specifying `-1` when there are no previously-visited pages in the session history), this method silently has no effect. Calling `go()` without parameters or a value of `0` reloads the current page. Internet Explorer lets you specify a string, instead of an integer, to go to a specific URL in the history list.

[`pushState()`](history/pushstate)  
Pushes the given data onto the session history stack with the specified title (and, if provided, URL). The data is treated as opaque by the DOM; you may specify any JavaScript object that can be serialized. Note that all browsers but Safari currently ignore the _title_ parameter. For more information, see [Working with the History API](history_api/working_with_the_history_api).

[`replaceState()`](history/replacestate)  
Updates the most recent entry on the history stack to have the specified data, title, and, if provided, URL. The data is treated as opaque by the DOM; you may specify any JavaScript object that can be serialized. Note that all browsers but Safari currently ignore the _title_ parameter. For more information, see [Working with the History API](history_api/working_with_the_history_api).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#the-history-interface">HTML Living Standard<br />
<span class="small">The definition of 'History' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Adds the <code>scrollRestoration</code> attribute.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#the-history-interface">HTML5<br />
<span class="small">The definition of 'History' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`History`

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

## See also

- The [`Window.history`](window/history) property returning the history of the current session.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/History" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/History</a>
