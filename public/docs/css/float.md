# float

The `float` CSS property places an element on the left or right side of its container, allowing text and inline elements to wrap around it. The element is removed from the normal flow of the page, though still remaining a part of the flow (in contrast to [absolute positioning](position#absolute_positioning)).

A _floating element_ is one where the computed value of `float` is not `none`.

As `float` implies the use of the block layout, it modifies the computed value of the [`display`](display) values, in some cases:

<table><thead><tr class="header"><th>Specified value</th><th>Computed value</th></tr></thead><tbody><tr class="odd"><td><code>inline</code></td><td><code>block</code></td></tr><tr class="even"><td><code>inline-block</code></td><td><code>block</code></td></tr><tr class="odd"><td><code>inline-table</code></td><td><code>table</code></td></tr><tr class="even"><td><code>table-row</code></td><td><code>block</code></td></tr><tr class="odd"><td><code>table-row-group</code></td><td><code>block</code></td></tr><tr class="even"><td><code>table-column</code></td><td><code>block</code></td></tr><tr class="odd"><td><code>table-column-group</code></td><td><code>block</code></td></tr><tr class="even"><td><code>table-cell</code></td><td><code>block</code></td></tr><tr class="odd"><td><code>table-caption</code></td><td><code>block</code></td></tr><tr class="even"><td><code>table-header-group</code></td><td><code>block</code></td></tr><tr class="odd"><td><code>table-footer-group</code></td><td><code>block</code></td></tr><tr class="even"><td><code>inline-flex</code></td><td><code>flex</code></td></tr><tr class="odd"><td><code>inline-grid</code></td><td><code>grid</code></td></tr><tr class="even"><td><em>other</em></td><td><em>unchanged</em></td></tr></tbody></table>

**Note:** If you're referring to this property from JavaScript as a member of the [`HTMLElement.style`](https://developer.mozilla.org/en-US/docs/Web/API/ElementCSSInlineStyle/style) object, modern browsers support `float`, but in older browsers you have to spell it as `cssFloat`, with Internet Explorer versions 8 and older using `styleFloat`. This was an exception to the rule, that the name of the DOM member is the camel-case name of the dash-separated CSS name (due to the fact that "float" is a reserved word in JavaScript, as seen in the need to escape "class" as "className" and escape &lt;label&gt;'s "for" as "htmlFor").

## Syntax

    /* Keyword values */
    float: left;
    float: right;
    float: none;
    float: inline-start;
    float: inline-end;

    /* Global values */
    float: inherit;
    float: initial;
    float: unset;

The `float` property is specified as a single keyword, chosen from the list of values below.

### Values

`left`  
The element must float on the left side of its containing block.

`right`  
The element must float on the right side of its containing block.

`none`  
The element must not float.

`inline-start`  
The element must float on the start side of its containing block. That is the left side with `ltr` scripts, and the right side with `rtl` scripts.

`inline-end`  
The element must float on the end side of its containing block. That is the right side with `ltr` scripts, and the left side with `rtl` scripts.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, but has no effect if the value of <a href="display"><code>display</code></a> is <code>none</code>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    left | right | none | inline-start | inline-end

## Examples

### How floated elements are positioned

As mentioned above, when an element is floated, it is taken out of the normal flow of the document (though still remaining part of it). It is shifted to the left, or right, until it touches the edge of its containing box, _or another floated element_.

In this example, there are three colored squares. Two are floated left, and one is floated right. Note that the second "left" square is placed to the right of the first. Additional squares would continue to stack to the right, until they filled the containing box, after which they would wrap to the next line.

A floated element is at least as tall as its tallest nested floated children. We gave the parent `width: 100%` and floated it to ensure it is tall enough to encompass its floated children, and to make sure it takes up the width of the parent so we don't have to clear its adjacent sibling.

#### HTML

    <section>
      <div class="left">1</div>
      <div class="left">2</div>
      <div class="right">3</div>
      <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit.
         Morbi tristique sapien ac erat tincidunt, sit amet dignissim
         lectus vulputate. Donec id iaculis velit. Aliquam vel
         malesuada erat. Praesent non magna ac massa aliquet tincidunt
         vel in massa. Phasellus feugiat est vel leo finibus congue.</p>
    </section>

#### CSS

    section {
      border: 1px solid blue;
      width: 100%;
      float: left;
    }

    div {
      margin: 5px;
      width: 50px;
      height: 150px;
    }

    .left {
      float: left;
      background: pink;
    }

    .right {
      float: right;
      background: cyan;
    }

#### Result

### Clearing floats

Sometimes you may want to force an item to move below any floated elements. For instance, you may want paragraphs to remain adjacent to floats, but force headings to be on their own line. See [`clear`](clear) for examples.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#float-clear">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'float and clear' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds the values <code>inline-start</code> and <code>inline-end</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visuren.html#float-position">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'float' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#float">CSS Level 1<br />
<span class="small">The definition of 'float' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`float`

1

12

1

4

7

1

1

18

4

10.1

1

1.0

`flow_relative_values`

No

No

55

No

No

No

No

No

55

No

No

No

## See also

- [Block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context)
- Use [`clear`](clear) to force an item to move below a floated element.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/float" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/float</a>
