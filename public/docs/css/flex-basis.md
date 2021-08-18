# flex-basis

The `flex-basis` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the initial main size of a flex item. It sets the size of the content box unless otherwise set with [`box-sizing`](box-sizing).

In this example the [`flex-grow`](flex-grow) and [`flex-shrink`](flex-shrink) properties are both set to `1` on all three items, indicating that the flex item can grow and shrink from the initial `flex-basis`.

The demo then changes the `flex-basis` on the first item. It will then grow and shrink from that flex-basis. This means that, for example, when the `flex-basis` of the first item is `200px`, it will start out at 200px but then shrink to fit the space available with the other items being at least `min-content` sized.

<figure><img src="data:image/jpeg;base64,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" alt="The Flexbox Inspector in Firefox can help you understand the size items become." width="400" height="230" /><figcaption>The <a href="https://developer.mozilla.org/en-US/docs/Tools/Page_Inspector/How_to/Examine_Flexbox_layouts">Flexbox Inspector</a> in Firefox can help you understand the size items become.</figcaption></figure>**Note:**

**Note:** in case both `flex-basis` (other than `auto`) and `width` (or `height` in case of `flex-direction: column`) are set for an element, `flex-basis` has priority.

## Syntax

    /* Specify <'width'> */
    flex-basis: 10em;
    flex-basis: 3px;
    flex-basis: auto;

    /* Intrinsic sizing keywords */
    flex-basis: fill;
    flex-basis: max-content;
    flex-basis: min-content;
    flex-basis: fit-content;

    /* Automatically size based on the flex item’s content */
    flex-basis: content;

    /* Global values */
    flex-basis: inherit;
    flex-basis: initial;
    flex-basis: unset;

The `flex-basis` property is specified as either the keyword `content` or a `<'width'>`.

### Values

`<'width'>`  
An absolute [`<length>`](length), a [`<percentage>`](percentage) of the parent flex container's main size property, or the keyword `auto`. Negative values are invalid. Defaults to `auto`.

`content`  
Indicates automatic sizing, based on the flex item’s content.

**Note:** This value was not present in the initial release of Flexible Box Layout, and thus some older implementations will not support it. The equivalent effect can be had by using `auto` together with a main size ([width](https://drafts.csswg.org/css2/visudet.html#propdef-width) or [height](https://drafts.csswg.org/css2/visudet.html#propdef-height)) of `auto`.

**History:**

- Originally, `flex-basis:auto` meant "look at my `width` or `height` property".
- Then, `flex-basis:auto` was changed to mean automatic sizing, and "main-size" was introduced as the "look at my `width` or `height` property" keyword. It was implemented in [bug 1032922](https://bugzilla.mozilla.org/show_bug.cgi?id=1032922).
- Then, that change was reverted in [bug 1093316](https://bugzilla.mozilla.org/show_bug.cgi?id=1093316), so `auto` once again means "look at my `width` or `height` property"; and a new `content` keyword is being introduced to trigger automatic sizing. ([bug 1105111](https://bugzilla.mozilla.org/show_bug.cgi?id=1105111) covers adding that keyword).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>flex items, including in-flow pseudo-elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the flex container's inner main size</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="even"><td>Animation type</td><td>a <a href="length#interpolation">length</a>, <a href="percentage#interpolation">percentage</a> or calc();</td></tr></tbody></table>

## Formal syntax

    content | <'width'>

## Examples

### Setting flex item initial sizes

#### HTML

    <ul class="container">
      <li class="flex flex1">1: flex-basis test</li>
      <li class="flex flex2">2: flex-basis test</li>
      <li class="flex flex3">3: flex-basis test</li>
      <li class="flex flex4">4: flex-basis test</li>
      <li class="flex flex5">5: flex-basis test</li>
    </ul>

    <ul class="container">
      <li class="flex flex6">6: flex-basis test</li>
    </ul>

#### CSS

    .container {
      font-family: arial, sans-serif;
      margin: 0;
      padding: 0;
      list-style-type: none;
      display: flex;
      flex-wrap: wrap;
    }

    .flex {
      background: #6AB6D8;
      padding: 10px;
      margin-bottom: 50px;
      border: 3px solid #2E86BB;
      color: white;
      font-size: 14px;
      text-align: center;
      position: relative;
    }

    .flex:after {
      position: absolute;
      z-index: 1;
      left: 0;
      top: 100%;
      margin-top: 10px;
      width: 100%;
      color: #333;
      font-size: 12px;
    }

    .flex1 {
      flex-basis: auto;
    }

    .flex1:after {
      content: 'auto';
    }

    .flex2 {
      flex-basis: max-content;
    }

    .flex2:after {
      content: 'max-content';
    }

    .flex3 {
      flex-basis: min-content;
    }

    .flex3:after {
      content: 'min-content';
    }

    .flex4 {
      flex-basis: fit-content;
    }

    .flex4:after {
      content: 'fit-content';
    }

    .flex5 {
       flex-basis: content;
    }

    .flex5:after {
      content: 'content';
    }

    .flex6 {
      flex-basis: fill;
    }

    .flex6:after {
      content: 'fill';
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-flexbox-1/#propdef-flex-basis">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'flex-basis' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`flex-basis`

29

22

12

12

22

Since Firefox 28, multi-line flexbox is supported.

49

11

When a non-`auto` `flex-basis` is specified, Internet Explorer 10 and 11 always uses a `content-box` box model to calculate the size of a flex item, even if [`box-sizing: border-box`](https://developer.mozilla.org/docs/Web/CSS/box-sizing) is applied to the element. See [Flexbug \#7](https://github.com/philipwalton/flexbugs#7-flex-basis-doesnt-account-for-box-sizingborder-box) for more info.

12.1

15

9

7

4.4

≤37

29

25

22

Since Firefox 28, multi-line flexbox is supported.

49

12.1

14

9

7

2.0

1.5

`auto`

22

12

22

11

12.1

9

7

≤37

25

22

12.1

9

7

1.5

`content`

No

12-79

61

No

No

No

No

No

61

No

No

No

`max-content`

No

No

66

22

No

No

No

No

No

66

22

No

No

No

`min-content`

No

No

66

22

No

No

No

No

No

66

22

No

No

No

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Controlling Ratios of flex items along the main axis](css_flexible_box_layout/controlling_ratios_of_flex_items_along_the_main_ax)_
- [`width`](width)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/flex-basis</a>
