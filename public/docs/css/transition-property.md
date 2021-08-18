# transition-property

The `transition-property`[CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the CSS properties to which a [transition effect](css_transitions/using_css_transitions) should be applied.

**Note:** The [set of properties that can be animated](css_animated_properties) is subject to change. As such, you should avoid including any properties in the list that don't currently animate, as someday they might, causing unexpected results.

If you specify a shorthand property (e.g., [`background`](background)), all of its longhand sub-properties that can be animated will be.

## Syntax

    /* Keyword values */
    transition-property: none;
    transition-property: all;

    /* <custom-ident> values */
    transition-property: test_05;
    transition-property: -specific;
    transition-property: sliding-vertically;

    /* Multiple values */
    transition-property: test1, animation4;
    transition-property: all, height, color;
    transition-property: all, -moz-specific, sliding;

    /* Global values */
    transition-property: inherit;
    transition-property: initial;
    transition-property: unset;

### Values

`none`  
No properties will transition.

`all`  
All properties that can transition will.

[`<custom-ident>`](custom-ident)  
A string identifying the property to which a transition effect should be applied when its value changes.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>all</td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | <single-transition-property>#where
    <single-transition-property> = all | <custom-ident>

## Examples

### Simple example

This example performs a four-second font size transition when the user hovers over the element, the `transition-property` is the `font-size`.

#### HTML

    <a class="target">Hover over me</a>

#### CSS

    .target {
      font-size: 14px;
      transition-property: font-size;
      transition-duration: 4s;
    }

    .target:hover {
      font-size: 36px;
    }

You will find more examples of `transition-property` included in the main [CSS transitions](css_transitions/using_css_transitions) article.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#transition-property-property">CSS Transitions<br />
<span class="small">The definition of 'transition-property' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`transition-property`

26

1

12

12

16

4

49

44

10

10

12.1

15

11.6-15

9

3.1

≤37

≤37

26

18

16

4

49

44

12.1

14

12-14

9

2

1.5

1.0

`IDENT_value`

1

12

16

10

15

4

≤37

18

16

14

3

1.0

## See also

- [Using CSS transitions](css_transitions/using_css_transitions)
- [`transition`](transition)
- [`transition-duration`](transition-duration)
- [`transition-timing-function`](transition-timing-function)
- [`transition-delay`](transition-delay)
- [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transition-property</a>
