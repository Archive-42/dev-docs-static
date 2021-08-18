# Location: assign()

The `Location.assign()` method causes the window to load and display the document at the URL specified. After the navigation occurs, the user can navigate back to the page that called `Location.assign()` by pressing the "back" button.

If the assignment can't happen because of a security violation, a [`DOMException`](../domexception) of the `SECURITY_ERROR` type is thrown. This happens if the origin of the script calling the method is different from the origin of the page originally described by the [`Location`](../location) object, mostly when the script is hosted on a different domain.

If the provided URL is not valid, a [`DOMException`](../domexception) of the `SYNTAX_ERROR` type is thrown.

## Syntax

    location.assign(url);

### Parameters

`url`  
Is a [`DOMString`](../domstring) containing the URL of the page to navigate to.

## Example

    // Navigate to the Location.reload article
    window.location.assign('https://developer.mozilla.org/en-US/docs/Web/API/Location/reload');

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/history.html#dom-location-assign">HTML Living Standard<br />
<span class="small">The definition of 'Location.assign()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-location-assign">HTML5<br />
<span class="small">The definition of 'Location.assign()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`assign`

1

12

1

5.5

3

3

1

18

4

10.1

1

1.0

## See also

- The [`Location`](../location) interface it belongs to.
- Similar methods: [`Location.replace()`](replace) and [`Location.reload()`](reload).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/assign" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/assign</a>
