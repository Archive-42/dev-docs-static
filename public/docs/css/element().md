# element()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `element()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) defines an [`<image>`](image) value generated from an arbitrary HTML element. This image is live, meaning that if the HTML element is changed, the CSS properties using the resulting value are automatically updated.

A particularly useful scenario for using this would be to render an image in an HTML [`<canvas>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/canvas) element, then use that as a background.

On Gecko browsers, you can use the non-standard [`document.mozSetImageElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSetImageElement) method to change the element being used as the background for a given CSS background element.

## Syntax

    element(id)

where:

id  
The ID of an element to use as the background, specified using the HTML attribute \#_id_ on the element.

## Examples

These examples can be [viewed live](https://media.prod.mdn.mozit.cloud/samples/cssref/moz-element.html) in builds of Firefox that support `-moz-element()`.

### A somewhat realistic example

This example uses a hidden [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) as a background. The background element uses a gradient, but also includes text that is rendered as part of the background.

    <div style="width:400px; height:400px; background:-moz-element(#myBackground1) no-repeat;">
      <p>This box uses the element with the #myBackground1 ID as its background!</p>
    </div>

    <div style="overflow:hidden; height:0;">
      <div id="myBackground1" style="width:1024px; height:1024px; background-image: linear-gradient(to right, red, orange, yellow, white);">
      <p style="transform-origin:0 0; transform: rotate(45deg); color:white;">This text is part of the background. Cool, huh?</p>
      </div>
    </div>

The [`<div>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div) element with the ID "myBackground1" is used as the background for the content including the paragraph "This box uses the element with the \#myBackground1 ID as its background!".

<img src="data:image/png;base64,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" class="default internal" width="405" height="405" />

### A somewhat more bizarre example

This example uses a hidden [`<button>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button) element in a repeating pattern as its background. This demonstrates that you can use arbitrary elements as background, but doesn't necessarily demonstrate good design practices.

    <div style="width:400px; height:100px; background:-moz-element(#myBackground2);">
    </div>

    <div style="overflow:hidden; height:0;">
      <button id="myBackground2" type="button">Evil button!</button>
    </div>

<img src="data:image/png;base64,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" class="default internal" width="405" height="104" />

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-images-4/#element-notation">CSS Images Module Level 4<br />
<span class="small">The definition of 'Using Elements as Images: the element() notation' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Deferred from CSS3 Images.</td></tr></tbody></table>

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

`element()`

No

No

57

29-57

`-moz-element()` is limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image), [`background`](https://developer.mozilla.org/docs/Web/CSS/background), [`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image) and [`border-image-source`](https://developer.mozilla.org/docs/Web/CSS/border-image-source).

4-29

`-moz-element()` is limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image) and [`background`](https://developer.mozilla.org/docs/Web/CSS/background).

No

No

No

No

No

60

29-60

`-moz-element()` is limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image), [`background`](https://developer.mozilla.org/docs/Web/CSS/background), [`border-image`](https://developer.mozilla.org/docs/Web/CSS/border-image) and [`border-image-source`](https://developer.mozilla.org/docs/Web/CSS/border-image-source).

4-29

`-moz-element()` is limited to [`background-image`](https://developer.mozilla.org/docs/Web/CSS/background-image) and [`background`](https://developer.mozilla.org/docs/Web/CSS/background).

No

No

No

## See also

- [`image()`](<image()>)
- [`image-set()`](<image-set()>)
- [`<image>`](image)
- [`<gradient>`](gradient)
- [`element()`](<element()>)
- [`cross-fade()`](<cross-fade()>)
- [`document.mozSetImageElement()`](https://developer.mozilla.org/en-US/docs/Web/API/Document/mozSetImageElement)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/element()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/element()</a>
