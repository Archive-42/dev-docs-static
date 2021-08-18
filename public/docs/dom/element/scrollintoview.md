# Element.scrollIntoView()

The [`Element`](../element) interface's `scrollIntoView()` method scrolls the element's parent container such that the element on which `scrollIntoView()` is called is visible to the user

## Syntax

    element.scrollIntoView();
    element.scrollIntoView(alignToTop); // Boolean parameter
    element.scrollIntoView(scrollIntoViewOptions); // Object parameter

### Parameters

`alignToTop` <span class="badge inline optional">Optional</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value:

- If `true`, the top of the element will be aligned to the top of the visible area of the scrollable ancestor. Corresponds to `scrollIntoViewOptions: {block: "start", inline: "nearest"}`. This is the default value.
- If `false`, the bottom of the element will be aligned to the bottom of the visible area of the scrollable ancestor. Corresponds to `scrollIntoViewOptions: {block: "end", inline: "nearest"}`.

`scrollIntoViewOptions` <span class="badge inline optional">Optional</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Is an Object with the following properties:

`behavior` <span class="badge inline optional">Optional</span>  
Defines the transition animation.  
One of `auto` or `smooth`. Defaults to `auto`.

`block` <span class="badge inline optional">Optional</span>  
Defines vertical alignment.  
One of `start`, `center`, `end`, or `nearest`. Defaults to `start`.

`inline` <span class="badge inline optional">Optional</span>  
Defines horizontal alignment.  
One of `start`, `center`, `end`, or `nearest`. Defaults to `nearest`.

## Example

    var element = document.getElementById("box");

    element.scrollIntoView();
    element.scrollIntoView(false);
    element.scrollIntoView({block: "end"});
    element.scrollIntoView({behavior: "smooth", block: "end", inline: "nearest"});

## Notes

The element may not be scrolled completely to the top or bottom depending on the layout of other elements.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-scrollintoview">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Element.scrollIntoView()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`scrollIntoView`

1

79

17-79

The only parameter supported is `alignToTop`.

12-17

\["Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).", "No support for `smooth` behavior."\]

1

5

\["Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).", "No support for `smooth` behavior or `center` options."\]

≤12.1

3

No support for `smooth` behavior or `center` options.

1

18

4

≤12.1

1

No support for `smooth` behavior or `center` options.

1.0

`scrollIntoViewOptions`

61

The `block` and `inline` options support the values `start`, `center`, `end`, `nearest`.

79

The `block` and `inline` options support the values `start`, `center`, `end`, `nearest`.

36

\["No support for `inline` option.", "Before Firefox 58, `nearest` and `center` values for the `block` option was unsupported. See [bug 1389274](https://bugzil.la/1389274)."\]

No

48

The `block` and `inline` options support the values `start`, `center`, `end`, `nearest`.

No

61

The `block` and `inline` options support the values `start`, `center`, `end`, `nearest`.

61

The `block` and `inline` options support the values `start`, `center`, `end`, `nearest`.

36

\["No support for `inline` option.", "Before Firefox 58, `nearest` and `center` values for the `block` option was unsupported. See [bug 1389274](https://bugzil.la/1389274)."\]

45

The `block` and `inline` options support the values `start`, `center`, `end`, `nearest`.

No

8.0

The `block` and `inline` options support the values `start`, `center`, `end`, `nearest`.

## See also

- [`Element.scrollIntoViewIfNeeded()`](scrollintoviewifneeded) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollIntoView</a>
