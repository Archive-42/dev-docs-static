# animation-iteration-count

The `animation-iteration-count` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the number of times an animation sequence should be played before stopping.

If multiple values are specified, each time the animation is played the next value in the list is used, cycling back to the first value after the last one is used.

It is often convenient to use the shorthand property [`animation`](animation) to set all animation properties at once.

## Syntax

    /* Keyword value */
    animation-iteration-count: infinite;

    /* <number> values */
    animation-iteration-count: 3;
    animation-iteration-count: 2.4;

    /* Multiple values */
    animation-iteration-count: 2, 0, infinite;

The `animation-iteration-count` property is specified as one or more comma-separated values.

### Values

`infinite`  
The animation will repeat forever.

`<number>`  
The number of times the animation will repeat; this is `1` by default. You may specify non-integer values to play part of an animation cycle: for example, `0.5` will play half of the animation cycle. Negative values are invalid.

**Note**: When you specify multiple values on an `animation-*` property, they will be assigned to the animations specified in the [`animation-name`](animation-name) property in different ways depending on how many there are. For more information, see [Setting multiple animation property values](css_animations/using_css_animations#setting_multiple_animation_property_values).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>1</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <single-animation-iteration-count>#where
    <single-animation-iteration-count> = infinite | <number>

## Examples

### The animation will run 10 times.

#### HTML

    <div class="box"></div>

#### CSS

    .box {
      background-color: rebeccapurple;
      border-radius: 10px;
      width: 100px;
      height: 100px;
      animation-name: rotate;
      animation-duration: 0.7s;
      animation-iteration-count: 10;
    }

    @keyframes rotate {
      0% {
        transform: rotate(0);
      }
      100% {
        transform: rotate(360deg);
      }
    }

See [CSS animations](css_animations/using_css_animations) for examples.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#animation-iteration-count">CSS Animations Level 1<br />
<span class="small">The definition of 'animation-iteration-count' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`animation-iteration-count`

43

3

12

12

16

49

44

5

10

30

15

12.1-15

12-15

9

4

43

≤37

43

18

16

49

44

5

30

14

12.1-14

12-14

9

3.2

4.0

1.0

## See also

- [Using CSS animations](css_animations/using_css_animations)
- JavaScript [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent) API

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/animation-iteration-count</a>
