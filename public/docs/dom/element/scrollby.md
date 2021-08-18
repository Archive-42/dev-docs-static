# Element.scrollBy()

The `scrollBy()` method of the [`Element`](../element) interface scrolls an element by the given amount.

## Syntax

    element.scrollBy(x-coord, y-coord);
    element.scrollBy(options)

### Parameters

- `x-coord` is the horizontal pixel value that you want to scroll by.
- `y-coord` is the vertical pixel value that you want to scroll by.

\- or -

- `options` is a [`ScrollToOptions`](../scrolltooptions) dictionary.

## Examples

    // scroll an element
    element.scrollBy(300, 300);

Using `options`:

    element.scrollBy({
      top: 100,
      left: 100,
      behavior: 'smooth'
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-scrollby-options-options">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'element.scrollBy()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`scrollBy`

61

79

36

No

48

10.1

61

61

36

45

10.3

8.0

`ScrollToOptions`

61

79

Yes

No

48

No

61

61

Yes

45

No

8.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollBy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollBy</a>
