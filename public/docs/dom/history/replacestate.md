# History.replaceState()

The `History.replaceState()` method modifies the current history entry, replacing it with the `stateObj`, `title`, and `URL` passed in the method parameters. This method is particularly useful when you want to update the state object or URL of the current history entry in response to some user action.

## Syntax

    history.replaceState(stateObj, title, [url])

### Parameters

`stateObj`  
The state object is a JavaScript object which is associated with the history entry passed to the `replaceState` method. The state object can be `null`.

`title`  
[Most browsers currently ignore this parameter](https://github.com/whatwg/html/issues/2174), although they may use it in the future. Passing the empty string here should be safe against future changes to the method. Alternatively, you could pass a short title for the state.

`url` <span class="badge inline optional">Optional</span>  
The URL of the history entry. The new URL must be of the same origin as the current URL; otherwise replaceState throws an exception.

## Examples

Suppose https://www.mozilla.org/foo.html executes the following JavaScript:

    const stateObj = { foo: 'bar' };
    history.pushState(stateObj, '', 'bar.html');

The explanation of these two lines above can be found in the [Example of `pushState()` method](../history_api/working_with_the_history_api#example_of_pushstate_method) section of the [Working with the History API](../history_api/working_with_the_history_api) article. Then suppose `https://www.mozilla.org/bar.html` executes the following JavaScript:

    history.replaceState(stateObj, '', 'bar2.html');

This will cause the URL bar to display `https://www.mozilla.org/bar2.html`, but won't cause the browser to load `bar2.html` or even check that `bar2.html` exists.

Suppose now that the user navigates to `https://www.microsoft.com`, then clicks the Back button. At this point, the URL bar will display `https://www.mozilla.org/bar2.html`. If the user now clicks Back again, the URL bar will display https://www.mozilla.org/foo.html, and totally bypass bar.html.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/history.html#dom-history-replacestate">HTML Living Standard<br />
<span class="small">The definition of 'History.replaceState()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/history.html#dom-history-replacestate">HTML5<br />
<span class="small">The definition of 'History.replaceState()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`title`

No

No

No

No

No

Yes

No

No

No

No

?

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/History/replaceState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/History/replaceState</a>
