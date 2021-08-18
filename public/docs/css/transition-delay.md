# transition-delay

The `transition-delay` CSS property specifies the duration to wait before starting a property's [transition effect](css_transitions/using_css_transitions) when its value changes.

The delay may be zero, positive, or negative:

- A value of `0s` (or `0ms`) will begin the transition effect immediately.
- A positive value will delay the start of the transition effect for the given length of time.
- A negative value will begin the transition effect immediately, and partway through the effect. In other words, the effect will be animated as if it had already been running for the given length of time.

You may specify multiple delays, which is useful when transitioning multiple properties. Each delay will be applied to the corresponding property as specified by the [`transition-property`](transition-property) property, which acts as a master list. If there are fewer delays specified than in the master list, the list of delay values will be repeated until there are enough. If there are more delays, the list of delay values will be truncated to match the number of properties. In both cases, the CSS declaration remains valid.

## Syntax

    /* <time> values */
    transition-delay: 3s;
    transition-delay: 2s, 4ms;

    /* Global values */
    transition-delay: inherit;
    transition-delay: initial;
    transition-delay: unset;

### Values

[`<time>`](time)  
Denotes the amount of time to wait between a property's value changing and the start of the transition effect.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0s</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <time>#

## Examples

### A series of examples with different delays set

`transition-delay: 0.5s`

`transition-delay: 1s`

`transition-delay: 2s`

`transition-delay: 4s`

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#transition-delay-property">CSS Transitions<br />
<span class="small">The definition of 'transition-delay' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`transition-delay`

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

4

≤37

2

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

## See also

- [Using CSS transitions](css_transitions/using_css_transitions)
- [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent) API

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transition-delay</a>
