# Class selectors

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) **class selector** matches elements based on the contents of their [`class`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-class) attribute.

    /* All elements with class="spacious" */
    .spacious {
      margin: 2em;
    }

    /* All <li> elements with class="spacious" */
    li.spacious {
      margin: 2em;
    }

    /* All <li> elements with a class list that includes both "spacious" and "elegant" */
    /* For example, class="elegant retro spacious" */
    li.spacious.elegant {
      margin: 2em;
    }

## Syntax

    .class_name { style properties }

Note that this is equivalent to the following [`attribute selector`](attribute_selectors):

    [class~=class_name] { style properties }

## Examples

### CSS

    .red {
      color: #f33;
    }

    .yellow-bg {
      background: #ffa;
    }

    .fancy {
      font-weight: bold;
      text-shadow: 4px 4px 3px #77f;
    }

### HTML

    <p class="red">This paragraph has red text.</p>
    <p class="red yellow-bg">This paragraph has red text and a yellow background.</p>
    <p class="red fancy">This paragraph has red text and "fancy" styling.</p>
    <p>This is just a regular paragraph.</p>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#class-html">Selectors Level 4<br />
<span class="small">The definition of 'class selectors' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>No changes</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#class-html">Selectors Level 3<br />
<span class="small">The definition of 'class selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/selector.html#class-html">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'child selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#class-as-selector">CSS Level 1<br />
<span class="small">The definition of 'child selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`Class_selectors`

1

12

1

3

3.5

1

≤37

18

4

10.1

1

1.0

## See also

- [CSS Selectors](css_selectors)
- [Learn CSS: Selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Selectors)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors</a>
