# transition-duration

The `transition-duration` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the length of time a transition animation should take to complete. By default, the value is `0s`, meaning that no animation will occur.

You may specify multiple durations; each duration will be applied to the corresponding property as specified by the [`transition-property`](transition-property) property, which acts as a master list. If there are fewer durations specified than in the master list, the user agent repeat the list of durations. If there are more durations, the list is truncated to the right size. In both case the CSS declaration stays valid.

## Syntax

    /* <time> values */
    transition-duration: 6s;
    transition-duration: 120ms;
    transition-duration: 1s, 15s;
    transition-duration: 10s, 30s, 230ms;

    /* Global values */
    transition-duration: inherit;
    transition-duration: initial;
    transition-duration: unset;

### Values

`<time>`  
Is a [`<time>`](time) denoting the amount of time the transition from the old value of a property to the new value should take. A time of `0s` indicates that no transition will happen, that is the switch between the two states will be instantaneous. A negative value for the time renders the declaration invalid.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0s</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <time>#

## Examples

### A series of examples with increasing durations

`transition-duration: 0.5s`

`transition-duration: 1s`

`transition-duration: 2s`

`transition-duration: 4s`

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#transition-duration-property">CSS Transitions<br />
<span class="small">The definition of 'transition-duration' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`transition-duration`

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

10-15

9

3.1

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

10.1-14

9

2

1.5

1.0

## See also

- [Using CSS transitions](css_transitions/using_css_transitions)
- [`transition`](transition)
- [`transition-property`](transition-property)
- [`transition-timing-function`](transition-timing-function)
- [`transition-delay`](transition-delay)
- [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transition-duration</a>
