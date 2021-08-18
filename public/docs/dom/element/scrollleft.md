# Element.scrollLeft

The `Element.scrollLeft` property gets or sets the number of pixels that an element's content is scrolled from its left edge.

If the element's [`direction`](https://developer.mozilla.org/en-US/docs/Web/CSS/direction) is `rtl` (right-to-left), then `scrollLeft` is `0` when the scrollbar is at its rightmost position (at the start of the scrolled content), and then increasingly negative as you scroll towards the end of the content.

On systems using display scaling, `scrollLeft` may give you a decimal value.

## Syntax

### Getting the value

    // Get the number of pixels scrolled
    var sLeft = element.scrollLeft;

`sLeft` is an integer representing the number of pixels that `element` has been scrolled from the left edge.

### Setting the value

    // Set the number of pixels scrolled
    element.scrollLeft = 10;

`scrollLeft` can be specified as any integer value. However:

- If the element can't be scrolled (e.g., it has no overflow), `scrollLeft` is set to `0`.
- If specified as a value less than `0` (greater than `0` for right-to-left elements), `scrollLeft` is set to `0`.
- If specified as a value greater than the maximum that the content can be scrolled, `scrollLeft` is set to the maximum.

## Example

### HTML

    <div id="container">
      <div id="content">Click the button to slide right!</div>
    </div>

    <button id="slide" type="button">Slide right</button>

### CSS

    #container {
      width: 100px;
      height: 100px;
      border: 1px solid #ccc;
      overflow-x: scroll;
    }

    #content {
      width: 250px;
      background-color: #ccc;
    }

### JavaScript

    const button = document.getElementById('slide');

    button.onclick = function () {
      document.getElementById('container').scrollLeft += 20;
    };

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-scrollleft">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'scrollLeft' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`scrollLeft`

1

For right-to-left elements, this property uses 0-100 (most left to most right) instead of negative values. See [bug 721759](https://crbug.com/721759).

12

\["From Edge 79, for right-to-left elements, this property uses 0-100 (most left to most right) instead of negative values. See [bug 721759](https://crbug.com/721759).", "Before Edge 79, for right-to-left elements, this property uses 100-0 (most left to most right) instead of negative values."\]

1

5

For right-to-left elements, this property uses 100-0 (most left to most right) instead of negative values.

8

1

1

For right-to-left elements, this property uses 0-100 (most left to most right) instead of negative values. See [bug 721759](https://crbug.com/721759).

18

For right-to-left elements, this property uses 0-100 (most left to most right) instead of negative values. See [bug 721759](https://crbug.com/721759).

4

10.1

1

1.0

For right-to-left elements, this property uses 0-100 (most left to most right) instead of negative values. See [bug 721759](https://crbug.com/721759).

## See also

- [MSDN's Measuring Element Dimension and Location](<https://msdn.microsoft.com/en-us/library/hh781509(v=vs.85).aspx>)
- [`Element.scrollTop`](scrolltop)
- [`Element.scrollTo()`](scrollto)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeft" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollLeft</a>
