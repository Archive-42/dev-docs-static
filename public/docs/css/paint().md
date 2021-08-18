# paint()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `paint()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) defines an [`<image>`](image) value generated with a PaintWorklet.

## Syntax

    paint(workletName, parameters)

where:

workletName  
The name of the registered worklet.

parameters  
Optional additional parameters to pass to the paintWorklet

## Examples

### Basic usage example

You can pass additional arguments via the CSS paint() function. In this example, we passed two arguments: whether the background-image on a group of list items is filled or just has a stroke outline, and the width of that outline:

    li {
       --boxColor: hsla(55, 90%, 60%, 1.0);
       background-image: paint(hollowHighlights, stroke, 2px);
    }

    li:nth-of-type(3n) {
       --boxColor: hsla(155, 90%, 60%, 1.0);
       background-image: paint(hollowHighlights, filled,  3px);
    }

    li:nth-of-type(3n+1) {
       --boxColor: hsla(255, 90%, 60%, 1.0);
       background-image: paint(hollowHighlights, stroke, 1px);
    }

We've included a custom property in the selector block defining a boxColor. Custom properties are accessible to the PaintWorklet.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-paint-api-1/#paint-notation">CSS Painting API Level 1<br />
<span class="small">The definition of 'Paint Notation' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`paint()`

65

79

No

No

52

No

65

65

No

47

No

9.2

## See also

- [`PaintWorklet`](https://developer.mozilla.org/en-US/docs/Web/API/PaintWorklet)
- [`CSS Painting API`](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API)
- [Using the CSS Painting API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API/Guide)
- [`<image>`](image)
- [`canvas`](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/paint()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/paint()</a>
