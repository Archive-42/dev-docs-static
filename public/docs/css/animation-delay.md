# animation-delay

The `animation-delay` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the amount of time to wait from applying the animation to an element before beginning to perform the animation. The animation can start later, immediately from its beginning, or immediately and partway through the animation.

It is often convenient to use the shorthand property [`animation`](animation) to set all animation properties at once.

## Syntax

    /* Single animation */
    animation-delay: 3s;
    animation-delay: 0s;
    animation-delay: -1500ms;

    /* Multiple animations */
    animation-delay: 2.1s, 480ms;

### Values

`<time>`  
The time offset, from the moment at which the animation is applied to the element, at which the animation should begin. This may be specified in either seconds (`s`) or milliseconds (`ms`). The unit is required.

A positive value indicates that the animation should begin after the specified amount of time has elapsed. A value of `0s`, which is the default, indicates that the animation should begin as soon as it's applied.

A negative value causes the animation to begin immediately, but partway through its cycle. For example, if you specify `-1s` as the animation delay time, the animation will begin immediately but will start 1 second into the animation sequence. If you specify a negative value for the animation delay, but the starting value is implicit, the starting value is taken from the moment the animation is applied to the element.

**Note**: When you specify multiple comma-separated values on an `animation-*` property, they will be assigned to the animations specified in the [`animation-name`](animation-name) property in different ways depending on how many there are. For more information, see [Setting multiple animation property values](css_animations/using_css_animations#setting_multiple_animation_property_values).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0s</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <time>#

## Examples

### The animation has a delay of 2 seconds

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
      animation-delay: 2s;
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#animation-delay">CSS Animations Level 1<br />
<span class="small">The definition of 'animation-delay' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`animation-delay`

43

3

12

16

Before Firefox 57, Firefox does not repaint elements outside the viewport that are animated into the viewport with a delay. This bug affects only some platforms, such as Windows.

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay</a>
