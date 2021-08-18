# flex-wrap

The `flex-wrap` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether flex items are forced onto one line or can wrap onto multiple lines. If wrapping is allowed, it sets the direction that lines are stacked.

See [Using CSS flexible boxes](css_flexible_box_layout/basic_concepts_of_flexbox) for more properties and information.

## Syntax

    flex-wrap: nowrap; /* Default value */
    flex-wrap: wrap;
    flex-wrap: wrap-reverse;

    /* Global values */
    flex-wrap: inherit;
    flex-wrap: initial;
    flex-wrap: unset;

The `flex-wrap` property is specified as a single keyword chosen from the list of values below.

### Values

The following values are accepted:

`nowrap`  
The flex items are laid out in a single line which may cause the flex container to overflow. The **cross-start** is either equivalent to **start** or **before** depending on the [`flex-direction`](flex-direction) value. This is the default value.

`wrap`  
The flex items break into multiple lines. The **cross-start** is either equivalent to **start** or **before** depending `flex-direction` value and the **cross-end** is the opposite of the specified **cross-start**.

`wrap-reverse`  
Behaves the same as `wrap` but **cross-start** and **cross-end** are permuted.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>nowrap</code></td></tr><tr class="even"><td>Applies to</td><td>flex containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    nowrap | wrap | wrap-reverse

## Examples

### Setting flex container wrap values

#### HTML

    <h4>This is an example for flex-wrap:wrap </h4>
    <div class="content">
      <div class="red">1</div>
      <div class="green">2</div>
      <div class="blue">3</div>
    </div>
    <h4>This is an example for flex-wrap:nowrap </h4>
    <div class="content1">
      <div class="red">1</div>
      <div class="green">2</div>
      <div class="blue">3</div>
    </div>
    <h4>This is an example for flex-wrap:wrap-reverse </h4>
    <div class="content2">
      <div class="red">1</div>
      <div class="green">2</div>
      <div class="blue">3</div>
    </div>

#### CSS

    /* Common Styles */
    .content,
    .content1,
    .content2 {
        color: #fff;
        font: 100 24px/100px sans-serif;
        height: 150px;
        text-align: center;
    }

    .content div,
    .content1 div,
    .content2 div {
        height: 50%;
        width: 300px;
    }
    .red {
        background: orangered;
    }
    .green {
        background: yellowgreen;
    }
    .blue {
        background: steelblue;
    }

    /* Flexbox Styles */
    .content {
        display: flex;
        flex-wrap: wrap;
    }
    .content1 {
        display: flex;
        flex-wrap: nowrap;
    }
    .content2 {
        display: flex;
        flex-wrap: wrap-reverse;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-flexbox-1/#flex-wrap-property">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'flex-wrap' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr></tbody></table>

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

`flex-wrap`

29

21

12

28

11

Partial support due to large number of bugs present. See [Flexbugs](https://github.com/philipwalton/flexbugs).

17

9

6.1

4.4

≤37

29

25

52

18

9

6.1

2.0

1.5

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Mastering wrapping of flex items](css_flexible_box_layout/mastering_wrapping_of_flex_items)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/flex-wrap</a>
