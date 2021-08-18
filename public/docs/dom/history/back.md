History.back()
==============

The `History.back()` method causes the browser to move back one page in the session history. It has the same effect as calling [`history.go(-1)`](go). If there is no previous page, this method call does nothing.

This method is [asynchronous](https://developer.mozilla.org/en-US/docs/Glossary/Asynchronous). Add a listener for the `popstate` event in order to determine when the navigation has completed.

Syntax
------

    history.back()

Examples
--------

The following short example causes a button on the page to navigate back one entry in the session history.

### HTML

    <button id="go-back">Go back!</button>

### JavaScript

    document.getElementById('go-back').addEventListener('click', () => {
      history.back();
    });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/history.html#history">HTML Living Standard<br />
<span class="small">The definition of 'History.back()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-history-back">HTML5<br />
<span class="small">The definition of 'History.back()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [`History`](../history)
-   [Working with the History API](../history_api/working_with_the_history_api)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/History/back" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/History/back</a>
