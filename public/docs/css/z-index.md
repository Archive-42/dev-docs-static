# z-index

The `z-index` CSS property sets the z-order of a [positioned](position) element and its descendants or flex items. Overlapping elements with a larger z-index cover those with a smaller one.

For a positioned box (that is, one with any `position` other than `static`), the `z-index` property specifies:

1.  The stack level of the box in the current [stacking context](css_positioning/understanding_z_index/the_stacking_context).
2.  Whether the box establishes a local stacking context.

## Syntax

    /* Keyword value */
    z-index: auto;

    /* <integer> values */
    z-index: 0;
    z-index: 3;
    z-index: 289;
    z-index: -1; /* Negative values to lower the priority */

    /* Global values */
    z-index: inherit;
    z-index: initial;
    z-index: unset;

The `z-index` property is specified as either the keyword `auto` or an `<integer>`.

### Values

`auto`  
The box does not establish a new local stacking context. The stack level of the generated box in the current stacking context is `0`.

`<integer>`  
This [`<integer>`](integer) is the stack level of the generated box in the current stacking context. The box also establishes a local stacking context. This means that the z-indexes of descendants are not compared to the z-indexes of elements outside this element.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>positioned elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>an <a href="integer#interpolation">integer</a></td></tr><tr class="even"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    auto | <integer>

## Examples

### Visually layering elements

#### HTML

    <div class="wrapper">
      <div class="dashed-box">Dashed box</div>
      <div class="gold-box">Gold box</div>
      <div class="green-box">Green box</div>
    </div>

#### CSS

    .wrapper {
      position: relative;
    }

    .dashed-box {
      position: relative;
      z-index: 1;
      border: dashed;
      height: 8em;
      margin-bottom: 1em;
      margin-top: 2em;
    }
    .gold-box {
      position: absolute;
      z-index: 3; /* put .gold-box above .green-box and .dashed-box */
      background: gold;
      width: 80%;
      left: 60px;
      top: 3em;
    }
    .green-box {
      position: absolute;
      z-index: 2; /* put .green-box above .dashed-box */
      background: lightgreen;
      width: 20%;
      left: 65%;
      top: -25px;
      height: 7em;
      opacity: 0.9;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/CSS2/visuren.html#z-index">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'z-index' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`z-index`

1

12

1

4

4

1

≤37

18

4

14

1

1.0

`negative_values`

1

12

3

4

4

1

≤37

18

4

14

1

1.0

## See also

- CSS [`position`](position) property
- [Understanding CSS z-indexes](css_positioning/understanding_z_index)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/z-index" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/z-index</a>
