# transition

The `transition` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property is a [shorthand property](shorthand_properties) for [`transition-property`](transition-property), [`transition-duration`](transition-duration), [`transition-timing-function`](transition-timing-function), and [`transition-delay`](transition-delay).

Transitions enable you to define the transition between two states of an element. Different states may be defined using [pseudo-classes](pseudo-classes) like [`:hover`](:hover) or [`:active`](:active) or dynamically set using JavaScript.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`transition-delay`](transition-delay)
- [`transition-duration`](transition-duration)
- [`transition-property`](transition-property)
- [`transition-timing-function`](transition-timing-function)

## Syntax

    /* Apply to 1 property */
    /* property name | duration */
    transition: margin-right 4s;

    /* property name | duration | delay */
    transition: margin-right 4s 1s;

    /* property name | duration | easing function */
    transition: margin-right 4s ease-in-out;

    /* property name | duration | easing function | delay */
    transition: margin-right 4s ease-in-out 1s;

    /* Apply to 2 properties */
    transition: margin-right 4s, color 1s;

    /* Apply to all changed properties */
    transition: all 0.5s ease-out;

    /* Global values */
    transition: inherit;
    transition: initial;
    transition: unset;

The `transition` property is specified as one or more single-property transitions, separated by commas.

Each single-property transition describes the transition that should be applied to a single property (or the special values `all` and `none`). It includes:

- zero or one value representing the property to which the transition should apply. This may be any one of:
  - the keyword `none`
  - the keyword `all`
  - a [`<custom-ident>`](custom-ident) naming a CSS property.
- zero or one [`<easing-function>`](easing-function) value representing the easing function to use
- zero, one, or two [`<time>`](time) values. The first value that can be parsed as a time is assigned to the [`transition-duration`](transition-duration), and the second value that can be parsed as a time is assigned to [`transition-delay`](transition-delay).

See [how things are handled](css_transitions/using_css_transitions#when_property_value_lists_are_of_different_lengths) when lists of property values aren't the same length. In short, extra transition descriptions beyond the number of properties actually being animated are ignored.

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="transition-delay"><code>transition-delay</code></a>: <code>0s</code></li><li><a href="transition-duration"><code>transition-duration</code></a>: <code>0s</code></li><li><a href="transition-property"><code>transition-property</code></a>: all</li><li><a href="transition-timing-function"><code>transition-timing-function</code></a>: <code>ease</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="transition-delay"><code>transition-delay</code></a>: as specified</li><li><a href="transition-duration"><code>transition-duration</code></a>: as specified</li><li><a href="transition-property"><code>transition-property</code></a>: as specified</li><li><a href="transition-timing-function"><code>transition-timing-function</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <single-transition>#where
    <single-transition> = [ none | <single-transition-property> ] || <time> || <easing-function> || <time>where
    <single-transition-property> = all | <custom-ident>
    <easing-function> = linear | <cubic-bezier-timing-function> | <step-timing-function>where
    <cubic-bezier-timing-function> = ease | ease-in | ease-out | ease-in-out | cubic-bezier([0,1]>, <number>, [0,1]>, <number>)
    <step-timing-function> = step-start | step-end | steps(<integer>[, <step-position>]?)where
    <step-position> = jump-start | jump-end | jump-none | jump-both | start | end

## Examples

### Simple example

This example performs a four-second font size transition with a one-second delay when the user hovers over the element.

#### HTML

    <a class="target">Hover over me</a>

#### CSS

    .target {
      font-size: 14px;
      transition: font-size 4s 1s;
    }

    .target:hover {
      font-size: 36px;
    }

There are several more examples of CSS transitions included in the [Using CSS transitions](css_transitions/using_css_transitions) article.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#transition-shorthand-property">CSS Transitions<br />
<span class="small">The definition of 'transition' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`transition`

26

1

12

12

16

\["Before Firefox 57, transitions do not work when transitioning from a [`text-shadow`](https://developer.mozilla.org/docs/Web/CSS/text-shadow) with a color specified to a `text-shadow` without a color specified (see [bug 726550](https://bugzil.la/726550)).", "Before Firefox 57, cancelling a filling animation (for example, with `animation-fill-mode: forwards` set) can trigger a transition set on the same element, although only once (see [bug 1192592](https://bugzil.la/1192592) and [these test cases](https://bug1192592.bmoattachments.org/attachment.cgi?id=8843824) for more information).", "Before Firefox 57, the [`background-position`](https://developer.mozilla.org/docs/Web/CSS/background-position) property can't be transitioned between two values containing different numbers of [`<position>`](https://developer.mozilla.org/docs/Web/CSS/position_value) values, for example `background-position: 10px 10px;` and `background-position: 20px 20px, 30px 30px;` (see [bug 1390446](https://bugzil.la/1390446))."\]

4

49

44

10

10

12.1

15

10.1-15

9

3.1

≤37

2

26

18

16

\["Before Firefox 57, transitions do not work when transitioning from a [`text-shadow`](https://developer.mozilla.org/docs/Web/CSS/text-shadow) with a color specified to a `text-shadow` without a color specified (see [bug 726550](https://bugzil.la/726550)).", "Before Firefox 57, cancelling a filling animation (for example, with `animation-fill-mode: forwards` set) can trigger a transition set on the same element, although only once (see [bug 1192592](https://bugzil.la/1192592) and [these test cases](https://bug1192592.bmoattachments.org/attachment.cgi?id=8843824) for more information).", "Before Firefox 57, the [`background-position`](https://developer.mozilla.org/docs/Web/CSS/background-position) property can't be transitioned between two values containing different numbers of [`<position>`](https://developer.mozilla.org/docs/Web/CSS/position_value) values, for example `background-position: 10px 10px;` and `background-position: 20px 20px, 30px 30px;` (see [bug 1390446](https://bugzil.la/1390446))."\]

4

49

44

12.1

14

10.1-14

9

2

1.5

1.0

`gradients`

No

12-79

No

10

No

No

No

No

No

No

No

No

## See also

- [Using CSS transitions](css_transitions/using_css_transitions)
- [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transition" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transition</a>
