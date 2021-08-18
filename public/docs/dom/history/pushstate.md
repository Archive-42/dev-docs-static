History.pushState()
===================

In an [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) document, the `history.pushState()` method adds an entry to the browser's session history stack.

Syntax
------

    history.pushState(state, title [, url])

### Parameters

`state`  
The `state` object is a JavaScript object which is associated with the new history entry created by `pushState()`. Whenever the user navigates to the new `state`, a `popstate` event is fired, and the `state` property of the event contains a copy of the history entry's `state` object.

The `state` object can be anything that can be serialized. Because Firefox saves `state` objects to the user's disk so they can be restored after the user restarts the browser, we impose a size limit of 2 MiB on the serialized representation of a `state` object. If you pass a `state` object whose serialized representation is larger than this to `pushState()`, the method will throw an exception. If you need more space than this, you're encouraged to use [`sessionStorage`](../window/sessionstorage) and/or [`localStorage`](../window/localstorage).

`title`  
[Most browsers currently ignore this parameter](https://github.com/whatwg/html/issues/2174), although they may use it in the future. Passing the empty string here should be safe against future changes to the method. Alternatively, you could pass a short title for the state to which you're moving. If you need the title to be changed you could use [`document.title`](../document/title).

 `url` <span class="badge inline optional">Optional</span>   
The new history entry's URL is given by this parameter. Note that the browser won't attempt to load this URL after a call to `pushState()`, but it might attempt to load the URL later, for instance after the user restarts the browser. The new URL does not need to be absolute; if it's relative, it's resolved relative to the current URL. The new URL must be of the same [origin](https://developer.mozilla.org/en-US/docs/Glossary/Origin) as the current URL; otherwise, `pushState()` will throw an exception. If this parameter isn't specified, it's set to the document's current URL.

Description
-----------

In a sense, calling `pushState()` is similar to setting `window.location = "#foo"`, in that both will also create and activate another history entry associated with the current document. But `pushState()` has a few advantages:

-   The new URL can be any URL in the same origin as the current URL. In contrast, setting [`window.location`](../window/location) keeps you at the same document only if you modify only the hash.
-   You don't have to change the URL if you don't want to. In contrast, setting `window.location = "#foo";` only creates a new history entry if the current hash isn't `#foo`.
-   You can associate arbitrary data with your new history entry. With the hash-based approach, you need to encode all of the relevant data into a short string.

Note that `pushState()` never causes a `hashchange` event to be fired, even if the new URL differs from the old URL only in its hash.

Examples
--------

This creates a new browser history entry setting the *state*, *title*, and *url*.

### JavaScript

    const state = { 'page_id': 1, 'user_id': 5 }
    const title = ''
    const url = 'hello-world.html'

    history.pushState(state, title, url)

### Change a query parameter

    const url = new URL(window.location);
    url.searchParams.set('foo', 'bar');
    window.history.pushState({}, '', url);

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/history.html#dom-history-pushstate">HTML Living Standard<br />
<span class="small">The definition of 'History.pushState()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/history.html#dom-history-pushstate">HTML5<br />
<span class="small">The definition of 'History.pushState()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

See also
--------

-   [Working with the History API](../history_api/working_with_the_history_api)
-   [Window: popstate event](../window/popstate_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/History/pushState" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/History/pushState</a>
