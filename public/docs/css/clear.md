# clear

The `clear` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether an element must be moved below (cleared) [floating](float) elements that precede it. The `clear` property applies to floating and non-floating elements.

When applied to non-floating blocks, it moves the [border edge](css_box_model/introduction_to_the_css_box_model#border-area) of the element down until it is below the [margin edge](css_box_model/introduction_to_the_css_box_model#margin-area) of all relevant floats. The non-floated block's top margin collapses.

Vertical margins between two floated elements on the other hand will not collapse. When applied to floating elements, the margin edge of the bottom element is moved below the margin edge of all relevant floats. This affects the position of later floats, since later floats cannot be positioned higher than earlier ones.

The floats that are relevant to be cleared are the earlier floats within the same [block formatting context](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Block_formatting_context).

If an element contains only floated elements, its height collapses to nothing. If you want it to always be able to resize, so that it contains floating elements inside it, you need to self-clear its children. This is called **clearfix**, and one way to do it is to add `clear` to a replaced [`::after`](::after) [pseudo-element](pseudo-elements) on it.

    #container::after {
      content: "";
      display: block;
      clear: both;
    }

## Syntax

    /* Keyword values */
    clear: none;
    clear: left;
    clear: right;
    clear: both;
    clear: inline-start;
    clear: inline-end;

    /* Global values */
    clear: inherit;
    clear: initial;
    clear: unset;

### Values

`none`  
Is a keyword indicating that the element is _not_ moved down to clear past floating elements.

`left`  
Is a keyword indicating that the element is moved down to clear past _left_ floats.

`right`  
Is a keyword indicating that the element is moved down to clear past _right_ floats.

`both`  
Is a keyword indicating that the element is moved down to clear past _both_ left and right floats.

`inline-start`  
Is a keyword indicating that the element is moved down to clear floats on _start side of its containing block_, that is the _left_ floats on ltr scripts and the _right_ floats on rtl scripts.

`inline-end`  
Is a keyword indicating that the element is moved down to clear floats on _end side of its containing block_, that is the _right_ floats on ltr scripts and the _left_ floats on rtl scripts.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>block-level elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | left | right | both | inline-start | inline-end

## Examples

### clear: left

#### HTML

    <div class="wrapper">
      <p class="black">Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Phasellus sit amet diam. Duis mattis varius dui. Suspendisse eget dolor.</p>
      <p class="red">Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</p>
      <p class="left">This paragraph clears left.</p>
    </div>

#### CSS

    .wrapper{
      border:1px solid black;
      padding:10px;
    }
    .left {
      border: 1px solid black;
      clear: left;
    }
    .black {
      float: left;
      margin: 0;
      background-color: black;
      color: #fff;
      width: 20%;
    }
    .red {
      float: left;
      margin: 0;
      background-color: pink;
      width:20%;
    }
    p {
      width: 50%;
    }

### clear: right

#### HTML

    <div class="wrapper">
      <p class="black">Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Phasellus sit amet diam. Duis mattis varius dui. Suspendisse eget dolor.</p>
      <p class="red">Lorem ipsum dolor sit amet, consectetuer adipiscing elit.</p>
      <p class="right">This paragraph clears right.</p>
    </div>

#### CSS

    .wrapper{
      border:1px solid black;
      padding:10px;
    }
    .right {
      border: 1px solid black;
      clear: right;
    }
    .black {
      float: right;
      margin: 0;
      background-color: black;
      color: #fff;
      width:20%;
    }
    .red {
      float: right;
      margin: 0;
      background-color: pink;
      width:20%;
    }
    p {
      width: 50%;
    }

### clear: both

#### HTML

    <div class="wrapper">
      <p class="black">Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Phasellus sit amet diam. Duis mattis varius dui. Suspendisse eget dolor. Fusce pulvinar lacus ac dui.</p>
      <p class="red">Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Phasellus sit amet diam. Duis mattis varius dui. Suspendisse eget dolor.</p>
      <p class="both">This paragraph clears both.</p>
    </div>

#### CSS

    .wrapper{
      border:1px solid black;
      padding:10px;
    }
    .both {
      border: 1px solid black;
      clear: both;
    }
    .black {
      float: left;
      margin: 0;
      background-color: black;
      color: #fff;
      width:20%;
    }
    .red {
      float: right;
      margin: 0;
      background-color: pink;
      width:20%;
    }
    p {
      width: 45%;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-logical/#float-clear">CSS Logical Properties and Values Level 1<br />
<span class="small">The definition of 'float and clear' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Adds the values <code>inline-start</code> and <code>inline-end</code></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/visuren.html#flow-control">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'clear' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No significant changes, though details are clarified.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/CSS1/#clear">CSS Level 1<br />
<span class="small">The definition of 'clear' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`clear`

1

12

1

4

3.5

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

- [CSS basic box model](css_box_model/introduction_to_the_css_box_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/clear" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/clear</a>
