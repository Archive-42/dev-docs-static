# animation-duration

The `animation-duration` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the length of time that an animation takes to complete one cycle.

It is often convenient to use the shorthand property [`animation`](animation) to set all animation properties at once.

## Syntax

    /* Single animation */
    animation-duration: 6s;
    animation-duration: 120ms;

    /* Multiple animations */
    animation-duration: 1.64s, 15.22s;
    animation-duration: 10s, 35s, 230ms;

### Values

`<time>`  
The time that an animation takes to complete one cycle. This may be specified in either seconds (`s`) or milliseconds (`ms`). The value must be positive or zero and the unit is required. A value of `0s`, which is the default value, indicates that no animation should occur.

**Note:** Negative values are invalid, causing the declaration to be ignored. Some early, prefixed, implementations may consider them as identical to `0s`.

**Note**: When you specify multiple comma-separated values on an `animation-*` property, they will be assigned to the animations specified in the [`animation-name`](animation-name) property in different ways depending on how many there are. For more information, see [Setting multiple animation property values](css_animations/using_css_animations#setting_multiple_animation_property_values).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0s</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <time>#

## Examples

### The animation has an animation-duration of 0.7 seconds

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
    }

    @keyframes rotate {
      0% {
        transform: rotate(0);
      }
      100% {
        transform: rotate(360deg);
      }
    }

See [CSS animations](css_animations/using_css_animations) for more examples.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#animation-duration">CSS Animations Level 1<br />
<span class="small">The definition of 'animation-duration' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`animation-duration`

43

3

12

12

16

49

44

5

10

Once the element has loaded, changing the value of this property has no effect.

30

15

12.1-15

12-15

9

4

43

2

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

4.2

4.0

1.0

## See also

- [Using CSS animations](css_animations/using_css_animations)
- JavaScript [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent) API

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/animation-duration</a>
