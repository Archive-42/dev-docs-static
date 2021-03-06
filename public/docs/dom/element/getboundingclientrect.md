# Element.getBoundingClientRect()

The `Element.getBoundingClientRect()` method returns a [`DOMRect`](../domrect) object providing information about the size of an element and its position relative to the [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport).

## Syntax

    domRect = element.getBoundingClientRect();

### Value

The returned value is a [`DOMRect`](../domrect) object which is the smallest rectangle which contains the entire element, including its padding and border-width. The `left`, `top`, `right`, `bottom`, `x`, `y`, `width`, and `height` properties describe the position and size of the overall rectangle in pixels. Properties other than `width` and `height` are relative to the top-left of the viewport.

<img src="data:image/png;base64,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" width="1466" height="1099" />

The `width` and `height` properties of the [`DOMRect`](../domrect) object returned by the method include the `padding` and `border-width`, not only the content width/height. In the standard box model, this would be equal to the `width` or `height` property of the element + `padding` + `border-width`. But if `box-sizing: border-box` is set for the element this would be directly equal to its `width` or `height`.

The returned value can be thought of as the union of the rectangles returned by [`getClientRects()`](getclientrects) for the element, i.e., the CSS border-boxes associated with the element.

Empty border-boxes are completely ignored. If all the element's border-boxes are empty, then a rectangle is returned with a `width` and `height` of zero and where the `top` and `left` are the top-left of the border-box for the first CSS box (in content order) for the element.

The amount of scrolling that has been done of the viewport area (or any other scrollable element) is taken into account when computing the bounding rectangle. This means that the rectangle's boundary edges (`top`, `right`, `bottom`, `left`) change their values every time the scrolling position changes (because their values are relative to the viewport and not absolute).

If you need the bounding rectangle relative to the top-left corner of the document, just add the current scrolling position to the `top` and `left` properties (these can be obtained using [`window.scrollX`](../window/scrollx) and [`window.scrollY`](../window/scrolly)) to get a bounding rectangle which is independent from the current scrolling position.

### Cross-browser fallback

Scripts requiring high cross-browser compatibility can use [`window.pageXOffset`](../window/pagexoffset) and [`window.pageYOffset`](../window/pageyoffset) instead of `window.scrollX` and `window.scrollY.` Scripts without access to these properties can use code like this:

    // For scrollX
    (((t = document.documentElement) || (t = document.body.parentNode))
      && typeof t.scrollLeft == 'number' ? t : document.body).scrollLeft
    // For scrollY
    (((t = document.documentElement) || (t = document.body.parentNode))
      && typeof t.scrollTop == 'number' ? t : document.body).scrollTop

## Examples

This simple example retrieves the `DOMRect` object representing the bounding client rect of a simple `<div>` element, and prints out its properties below it.

    <div></div>

    div {
      width: 400px;
      height: 200px;
      padding: 20px;
      margin: 50px auto;
      background: purple;
    }

    let elem = document.querySelector('div');
    let rect = elem.getBoundingClientRect();
    for (var key in rect) {
      if(typeof rect[key] !== 'function') {
        let para = document.createElement('p');
        para.textContent  = `${ key } : ${ rect[key] }`;
        document.body.appendChild(para);
      }
    }

Notice how the `width`/`height` are equal to its `width`/`height` + `padding`.

Also note how the values of `x`/`left`, `y`/`top`, `right`, and `bottom` are equal to the absolute distance from the relevant edge of the viewport to that side of the element, in each case.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-getboundingclientrect">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Element.getBoundingClientRect()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

### Notes

The returned `DOMRect` object can be modified in modern browsers. This was not true with older versions which effectively returned `DOMRectReadOnly`. With IE and Edge, not being able to add missing properties to their returned [`ClientRect`](<https://msdn.microsoft.com/en-us/library/hh826029(VS.85).aspx>), object prevents backfilling `x` and `y`.

Due to compatibility problems (see below), it is safest to rely on only properties `left`, `top`, `right`, and `bottom`.

Properties in the returned `DOMRect` object are not own properties. While the `in` operator and `for...in` will find returned properties, other APIs such as `Object.keys()` will fail. Moreover, and unexpectedly, the ES2015 and newer features such as `Object.assign()` and object rest/spread will fail to copy returned properties.

    rect = elt.getBoundingClientRect()
    // The result in emptyObj is {}
    emptyObj = Object.assign({}, rect)
    emptyObj = { ...rect }
    {width, ...emptyObj} = rect

`DOMRect` properties `top`, `left`, `right`, and `bottom` are computed using the values of the object's other properties.

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

`getBoundingClientRect`

2

12

3

4

9.5

4

2

18

4

10.1

3.2

Safari for iOS will modify the effective viewport based on the user zoom. This results in incorrect values whenever the user has zoomed.

1.0

## See also

- [`getClientRects()`](getclientrects)
- [MSDN: `getBoundingClientRect`](<https://msdn.microsoft.com/en-us/library/ms536433(VS.85).aspx>)
- [MSDN: `ClientRect`](<https://msdn.microsoft.com/en-us/library/hh826029(VS.85).aspx>), an earlier version of `DOMRect`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/getBoundingClientRect</a>
