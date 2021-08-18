# flex-shrink

The `flex-shrink` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the flex shrink factor of a flex item. If the size of all flex items is larger than the flex container, items shrink to fit according to `flex-shrink`.

In use, `flex-shrink` is used alongside the other flex properties [`flex-grow`](flex-grow) and [`flex-basis`](flex-basis), and normally defined using the [`flex`](flex) shorthand.

## Syntax

    /* <number> values */
    flex-shrink: 2;
    flex-shrink: 0.6;

    /* Global values */
    flex-shrink: inherit;
    flex-shrink: initial;
    flex-shrink: unset;

The `flex-shrink` property is specified as a single `<number>`.

### Values

`<number>`  
See [`<number>`](number). Negative values are invalid. Defaults to 1.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>1</code></td></tr><tr class="even"><td>Applies to</td><td>flex items, including in-flow pseudo-elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>a <a href="number#interpolation">number</a></td></tr></tbody></table>

## Formal syntax

    <number>

## Examples

### Setting flex item shrink factor

#### HTML

    <p>The width of content is 500px; the flex-basis of the flex items is 120px.</p>
    <p>A, B, C have flex-shrink:1 set. D and E have flex-shrink:2 set</p>
    <p>The width of D and E is less than the others.</p>
    <div id="content">
      <div class="box" style="background-color:red;">A</div>
      <div class="box" style="background-color:lightblue;">B</div>
      <div class="box" style="background-color:yellow;">C</div>
      <div class="box1" style="background-color:brown;">D</div>
      <div class="box1" style="background-color:lightgreen;">E</div>
    </div>

#### CSS

    #content {
      display: flex;
      width: 500px;
    }

    #content div {
      flex-basis: 120px;
      border: 3px solid rgba(0,0,0,.2);
    }

    .box {
      flex-shrink: 1;
    }

    .box1 {
      flex-shrink: 2;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-flexbox-1/#flex-shrink-property">CSS Flexible Box Layout Module<br />
<span class="small">The definition of 'flex-shrink' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`flex-shrink`

29

22

12

12

20

\["Since Firefox 28, multi-line flexbox is supported.", "Before Firefox 32, Firefox wasn't able to animate values starting or stopping at `0`."\]

49

10

Internet Explorer 10 uses `0` instead of `1` as the initial value for the `flex-shrink` property. A workaround is to always set an explicit value for `flex-shrink`. See [Flexbug \#6](https://github.com/philipwalton/flexbugs#6-the-default-flex-value-has-changed) for more info.

12.1

15

9

8

4.4

≤37

29

25

20

\["Since Firefox 28, multi-line flexbox is supported.", "Before Firefox 32, Firefox wasn't able to animate values starting or stopping at `0`."\]

49

12.1

14

9

8

2.0

1.5

## See also

- CSS Flexbox Guide: _[Basic Concepts of Flexbox](css_flexible_box_layout/basic_concepts_of_flexbox)_
- CSS Flexbox Guide: _[Controlling Ratios of flex items along the main axis](css_flexible_box_layout/controlling_ratios_of_flex_items_along_the_main_ax)_

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/flex-shrink</a>
