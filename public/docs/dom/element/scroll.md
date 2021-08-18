# Element.scroll()

The `scroll()` method of the [`Element`](../element) interface scrolls the element to a particular set of coordinates inside a given element.

## Syntax

    element.scroll(x-coord, y-coord)
    element.scroll(options)

### Parameters

#### Calling with coordinates

`x-coord`  
The pixel along the horizontal axis of the element that you want displayed in the upper left.

`y-coord`  
The pixel along the vertical axis of the element that you want displayed in the upper left.

#### Calling with `options`

`options`  
A [`ScrollToOptions`](../scrolltooptions) dictionary.

## Examples

    // Put the 1000th vertical pixel at the top of the element
    element.scroll(0, 1000);

Using `options`:

    element.scroll({
      top: 100,
      left: 100,
      behavior: 'smooth'
    });

## Specifications

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-scroll-options-options">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'element.scroll()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td><p>Initial definition.</p></td></tr></tbody></table>

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

`scroll`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/scroll</a>
