# ID selectors

The CSS **ID selector** matches an element based on the value of the element’s [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-id) attribute. In order for the element to be selected, its `id` attribute must match exactly the value given in the selector.

    /* The element with id="demo" */
    #demo {
      border: red 2px solid;
    }

## Syntax

    #id_value { style properties }

Note that syntactically (but not specificity-wise), this is equivalent to the following [`attribute selector`](attribute_selectors):

    [id=id_value] { style properties }

## Examples

### CSS

    #identified {
      background-color: skyblue;
    }

### HTML

    <div id="identified">This div has a special ID on it!</div>
    <div>This is just a regular div.</div>

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/selectors-4/#id-selectors">Selectors Level 4<br />
<span class="small">The definition of 'ID selectors' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-3/#id-selectors">Selectors Level 3<br />
<span class="small">The definition of 'ID selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/selector.html#id-selectors">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'ID selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS1/#id-as-selector">CSS Level 1<br />
<span class="small">The definition of 'ID selectors' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`ID_selectors`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/ID_selectors</a>
