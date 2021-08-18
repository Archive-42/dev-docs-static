History.state
=============

The `History.state` property returns a value representing the state at the top of the history stack. This is a way to look at the state without having to wait for a `popstate` event.

Syntax
------

    const currentState = history.state

### Value

The state at the top of the history stack. The value is [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) until the [`pushState()`](pushstate) or [`replaceState()`](replacestate) method is used.

Examples
--------

The code below logs the value of `history.state` before using the [`pushState()`](pushstate) method to push a value to the history. The next line logs the value to the console again, showing that `history.state` now has a value.

    // Should be null because we haven't modified the history stack yet
    console.log(`History.state before pushState: ${history.state}`);

    // Now push something on the stack
    history.pushState({name: 'Example'}, "pushState example", 'page3.html');

    // Now state has a value.
    console.log('History.state after pushState: ', history.state);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-history-state">HTML Living Standard<br />
<span class="small">The definition of 'History.state' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-history-state">HTML5<br />
<span class="small">The definition of 'History.state' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

-   [Working with the History API](../history_api/working_with_the_history_api)
-   [`History.pushState()`](pushstate)
-   [`History.replaceState()`](replacestate)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/History/state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/History/state</a>
