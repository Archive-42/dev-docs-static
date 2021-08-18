# animation-play-state

The `animation-play-state` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether an animation is running or paused.

Resuming a paused animation will start the animation from where it left off at the time it was paused, rather than starting over from the beginning of the animation sequence.

## Syntax

    /* Single animation */
    animation-play-state: running;
    animation-play-state: paused;

    /* Multiple animations */
    animation-play-state: paused, running, running;

    /* Global values */
    animation-play-state: inherit;
    animation-play-state: initial;
    animation-play-state: unset;

### Values

`running`  
The **animation** is currently **playing**.

`paused`  
The **animation** is currently **paused**.

**Note**: When you specify multiple comma-separated values on an `animation-*` property, they will be assigned to the animations specified in the [`animation-name`](animation-name) property in different ways depending on how many there are. For more information, see [Setting multiple animation property values](css_animations/using_css_animations#setting_multiple_animation_property_values).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>running</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <single-animation-play-state>#where
    <single-animation-play-state> = running | paused

## Examples

### The animation is paused

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
      animation-play-state: paused;
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#animation-play-state">CSS Animations Level 1<br />
<span class="small">The definition of 'animation-play-state' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`animation-play-state`

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

2

4.0

1.0

## See also

- [Using CSS animations](css_animations/using_css_animations)
- JavaScript [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent) API

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/animation-play-state</a>
