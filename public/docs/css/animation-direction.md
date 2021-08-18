# animation-direction

The `animation-direction` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether an animation should play forward, backward, or alternate back and forth between playing the sequence forward and backward.

It is often convenient to use the shorthand property [`animation`](animation) to set all animation properties at once.

## Syntax

    /* Single animation */
    animation-direction: normal;
    animation-direction: reverse;
    animation-direction: alternate;
    animation-direction: alternate-reverse;

    /* Multiple animations */
    animation-direction: normal, reverse;
    animation-direction: alternate, reverse, normal;

    /* Global values */
    animation-direction: inherit;
    animation-direction: initial;
    animation-direction: unset;

### Values

`normal`  
The animation plays _forwards_ each cycle. In other words, each time the animation cycles, the animation will reset to the beginning state and start over again. This is the default value.

`reverse`  
The animation plays _backwards_ each cycle. In other words, each time the animation cycles, the animation will reset to the end state and start over again. Animation steps are performed backwards, and timing functions are also reversed. For example, an `ease-in` timing function becomes `ease-out`.

`alternate`  
The animation reverses direction each cycle, with the first iteration being played _forwards_. The count to determine if a cycle is even or odd starts at one.

`alternate-reverse`  
The animation reverses direction each cycle, with the first iteration being played _backwards_. The count to determine if a cycle is even or odd starts at one.

**Note**: When you specify multiple comma-separated values on an `animation-*` property, they will be assigned to the animations specified in the [`animation-name`](animation-name) property in different ways depending on how many there are. For more information, see [Setting multiple animation property values](css_animations/using_css_animations#setting_multiple_animation_property_values).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <single-animation-direction>#where
    <single-animation-direction> = normal | reverse | alternate | alternate-reverse

## Examples

### The animation is playing reversed

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
      animation-direction: reverse;
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#animation-direction">CSS Animations Level 1<br />
<span class="small">The definition of 'animation-direction' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`animation-direction`

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

`alternate-reverse`

19

12

16

10

12.1

6

≤37

25

16

12.1

6

1.5

`reverse`

19

12

16

10

12.1

6

≤37

25

16

12.1

6

1.5

## See also

- [Using CSS animations](css_animations/using_css_animations)
- JavaScript [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent) API

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/animation-direction</a>
