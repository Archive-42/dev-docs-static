# HTMLImageElement.currentSrc

The read-only [`HTMLImageElement`](../htmlimageelement) property `currentSrc` indicates the URL of the image which is currently presented in the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element it represents.

## Syntax

    let currentSource = htmlImageElement.currentSrc;

### Value

A [`USVString`](../usvstring) indicating the full URL of the image currently visible in the [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element represented by the `HTMLImageElement`. This is useful when you provide multiple image options using the [`sizes`](sizes) and/or [`HTMLImageElement.srcset`](srcset) properties. `currentSrc` lets you determine which image from the set of provided images was selected by the browser.

## Example

In this example, two different sizes are provided for an image of a clock. One is 200px wide and the other is 400px wide. The [`sizes`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#attr-sizes) attribute is provided to indicate that the image should be drawn at 50% of the document width if the viewport is under 400px wide; otherwise, the image is drawn at 90% width of the document.

### HTML

     <img src="/files/16797/clock-demo-400px.png"
          alt="Clock"
          srcset="/files/16864/clock-demo-200px.png 200w, /files/16797/clock-demo-400px.png 400w"
          sizes="(max-width: 400px) 50%, 90%">

### JavaScript

    var clockImage = document.querySelector("img");
    let p = document.createElement("p");

    if (!clockImage.currentSrc.endsWith("200px.png")) {
      p.innerText = "Using the 200px image.";
    } else {
      p.innerText = "Using the 400px image!";
    }
    document.body.appendChild(p);

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-img-currentsrc">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.currentSrc' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`currentSrc`

38

13

38

No

25

9

38

38

38

25

9

3.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/currentSrc" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/currentSrc</a>
