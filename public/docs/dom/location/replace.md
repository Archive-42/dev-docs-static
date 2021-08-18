Location: replace()
===================

The `replace()` method of the [`Location`](../location) interface replaces the current resource with the one at the provided URL. The difference from the [`assign()`](assign) method is that after using `replace()` the current page will not be saved in session [`History`](../history), meaning the user won't be able to use the *back* button to navigate to it.

If the assignment can't happen because of a security violation, a [`DOMException`](../domexception) of the `SECURITY_ERROR` type is thrown. This happens if the origin of the script calling the method is different from the origin of the page originally described by the [`Location`](../location) object, mostly when the script is hosted on a different domain.

If the provided URL is not valid, a [`DOMException`](../domexception) of the `SYNTAX_ERROR` type is thrown.

Syntax
------

    object.replace(url);

### Parameters

`url`  
Is a [`DOMString`](../domstring) containing the URL of the page to navigate to.

Examples
--------

    // Navigate to the Location.reload article by replacing this page
    window.location.replace('https://developer.mozilla.org/en-US/docs/Web/API/Location.reload');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/history.html#dom-location-replace">HTML Living Standard<br />
<span class="small">The definition of 'Location.replace()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from <a href="https://www.w3.org/TR/html52/">HTML5</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-location-replace">HTML5<br />
<span class="small">The definition of 'Location.replace()' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`replace`

1

12

1

5.5

3

1

1

18

4

10.1

1

1.0

See also
--------

-   The [`Location`](../location) interface it belongs to.
-   Similar methods: [`Location.assign()`](assign) and [`Location.reload()`](reload).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Location/replace" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Location/replace</a>
