# CSSStyleDeclaration.length

The read-only property returns an integer that represents the number of style declarations in this CSS declaration block.

## Syntax

    var num = styles.length;

### Value

An integer that provides the number of styles explicitly set on the parent of the instance.

## Example

The following gets the number of explicitly set styles on the following HTML element:

    <div id="div1" style="margin: 0 10px; background-color: #CA1; font-family: monospace"></div>

JavaScript code:

    var myDiv = document.getElementById('div1'); var divStyle = myDiv.style; var len = divStyle.length; // 6

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstyledeclaration-length">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleDeclaration.length' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSStyleDeclaration">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSStyleDeclaration' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr></tbody></table>

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

`length`

44

12

1

9

≤12.1

6

4.4

18

4

≤12.1

Yes

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/length" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/length</a>
