# animation-name

The `animation-name` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property specifies the names of one or more [`@keyframes`](@keyframes) at-rules describing the animation or animations to apply to the element.

It is often convenient to use the shorthand property [`animation`](animation) to set all animation properties at once.

## Syntax

    /* Single animation */
    animation-name: none;
    animation-name: test_05;
    animation-name: -specific;
    animation-name: sliding-vertically;

    /* Multiple animations */
    animation-name: test1, animation4;
    animation-name: none, -moz-specific, sliding;

    /* Global values */
    animation-name: initial
    animation-name: inherit
    animation-name: unset

### Values

`none`  
A special keyword denoting no keyframes. It can be used to deactivate an animation without changing the ordering of the other identifiers, or to deactivate animations coming from the cascade.

[`<custom-ident>`](custom-ident)  
A name identifying the animation. This identifier is composed of a combination of case-sensitive letters `a` to `z`, numbers `0` to `9`, underscores (`_`), and/or dashes (`-`). The first non-dash character must be a letter. Also, two dashes are forbidden at the beginning of the identifier. Furthermore, the identifier can't be `none`, `unset`, `initial`, or `inherit`.

**Note**: When you specify multiple comma-separated values on an `animation-*` property, they will be assigned to the animations specified in the [`animation-name`](animation-name) property in different ways depending on how many there are. For more information, see [Setting multiple animation property values](css_animations/using_css_animations#setting_multiple_animation_property_values).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ none | <keyframes-name> ]#where
    <keyframes-name> = <custom-ident> | <string>

## Examples

### The animation has an animation-name of rotate

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

See [CSS animations](css_animations/using_css_animations) for examples.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#animation-name">CSS Animations Level 1<br />
<span class="small">The definition of 'animation-name' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`animation-name`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name</a>
