# Document.location

The `Document.location` read-only property returns a [`Location`](../location) object, which contains information about the URL of the document and provides methods for changing that URL and loading another URL.

Though `Document.location` is a _read-only_ `Location` object, you can also assign a [`DOMString`](../domstring) to it. This means that you can work with document.location as if it were a string in most cases: `document.location = 'http://www.example.com'` is a synonym of `document.location.href = 'http://www.example.com'`.If you assign another string to it, browser will load the website you assigned.

To retrieve just the URL as a string, the read-only [`document.URL`](url) property can also be used.

If the current document is not in a browsing context, the returned value is `null`.

## Syntax

    locationObj = document.location
    document.location = 'http://www.mozilla.org' // Equivalent to document.location.href = 'http://www.mozilla.org'

## Examples

    console.log(document.location);
    // Prints a Location object to the console

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/history.html#the-location-interface">HTML Living Standard<br />
<span class="small">The definition of 'Document.location' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#the-location-interface">HTML5<br />
<span class="small">The definition of 'Document.location' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`location`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

## See also

- The interface of the returned value, [`Location`](../location).
- A similar information, but attached to the [browsing context](https://developer.mozilla.org/en-US/docs/Glossary/Browsing_context), [`Window.location`](../window/location).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/location" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/location</a>
