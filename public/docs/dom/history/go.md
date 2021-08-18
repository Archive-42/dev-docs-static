History.go()
============

The `History.go()` method loads a specific page from the session history. You can use it to move forwards and backwards through the history depending on the value of a parameter.

This method is [asynchronous](https://developer.mozilla.org/en-US/docs/Glossary/Asynchronous). Add a listener for the `popstate` event in order to determine when the navigation has completed.

Syntax
------

    history.go([delta])

### Parameters

 `delta` <span class="badge inline optional">Optional</span>   
The position in the history to which you want to move, relative to the current page. A negative value moves backwards, a positive value moves forwards. So, for example, `history.go(2)` moves forward two pages and `history.go(-2)` moves back two pages. If no value is passed or if `delta` equals 0, it has the same result as calling `location.reload()`.

Examples
--------

To move back one page (the equivalent of calling [`back()`](back)):

    history.go(-1)

To move forward a page, just like calling [`forward()`](forward):

    history.go(1)

To move forward two pages:

    history.go(2);

To move backwards by two pages:

    history.go(-2);

And, finally either of the following statements will reload the current page:

    history.go();
    history.go(0);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/history.html#dom-history-go">HTML Living Standard<br />
<span class="small">The definition of 'History.go()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-history-go">HTML5<br />
<span class="small">The definition of 'History.go()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [`History`](../history)
-   [`back()`](back)
-   [`forward()`](forward)
-   `popstate` event
-   [Working with the History API](../history_api/working_with_the_history_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/History/go" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/History/go</a>
