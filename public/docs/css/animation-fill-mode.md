# animation-fill-mode

The `animation-fill-mode` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how a CSS animation applies styles to its target before and after its execution.

It is often convenient to use the shorthand property [`animation`](animation) to set all animation properties at once.

## Syntax

    /* Single animation */
    animation-fill-mode: none;
    animation-fill-mode: forwards;
    animation-fill-mode: backwards;
    animation-fill-mode: both;

    /* Multiple animations */
    animation-fill-mode: none, backwards;
    animation-fill-mode: both, forwards, none;

### Values

`none`  
The animation will not apply any styles to the target when it's not executing. The element will instead be displayed using any other CSS rules applied to it. This is the default value.

`forwards`  
The target will retain the computed values set by the last [keyframe](@keyframes) encountered during execution. The last keyframe depends on the value of [`animation-direction`](animation-direction) and [`animation-iteration-count`](animation-iteration-count):

<table><thead><tr class="header"><th><code>animation-direction</code></th><th><code>animation-iteration-count</code></th><th>last keyframe encountered</th></tr></thead><tbody><tr class="odd"><td><code>normal</code></td><td>even or odd</td><td><code>100%</code> or <code>to</code></td></tr><tr class="even"><td><code>reverse</code></td><td>even or odd</td><td><code>0%</code> or <code>from</code></td></tr><tr class="odd"><td><code>alternate</code></td><td>even</td><td><code>0%</code> or <code>from</code></td></tr><tr class="even"><td><code>alternate</code></td><td>odd</td><td><code>100%</code> or <code>to</code></td></tr><tr class="odd"><td><code>alternate-reverse</code></td><td>even</td><td><code>100%</code> or <code>to</code></td></tr><tr class="even"><td><code>alternate-reverse</code></td><td>odd</td><td><code>0%</code> or <code>from</code></td></tr></tbody></table>

`backwards`  
The animation will apply the values defined in the first relevant [keyframe](@keyframes) as soon as it is applied to the target, and retain this during the [`animation-delay`](animation-delay) period. The first relevant keyframe depends on the value of [`animation-direction`](animation-direction):

<table><thead><tr class="header"><th><code>animation-direction</code></th><th>first relevant keyframe</th></tr></thead><tbody><tr class="odd"><td><code>normal</code> or <code>alternate</code></td><td><code>0%</code> or <code>from</code></td></tr><tr class="even"><td><code>reverse</code> or <code>alternate-reverse</code></td><td><code>100%</code> or <code>to</code></td></tr></tbody></table>

`both`  
The animation will follow the rules for both forwards and backwards, thus extending the animation properties in both directions.

**Note**: When you specify multiple comma-separated values on an `animation-*` property, they will be assigned to the animations specified in the [`animation-name`](animation-name) property in different ways depending on how many there are. For more information, see [Setting multiple animation property values](css_animations/using_css_animations#setting_multiple_animation_property_values).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <single-animation-fill-mode>#where
    <single-animation-fill-mode> = none | forwards | backwards | both

## Examples

You can see the effect of `animation-fill-mode` in the following example. It demonstrates how, for an animation that runs for an infinite time, you can cause it to remain in its final state rather than reverting to the original state (which is the default).

### HTML

    <p>Move your mouse over the gray box!</p>
    <div class="demo">
     <div class="growsandstays">This grows and stays big.</div>
      <div class="grows">This just grows.</div>
    </div>

### CSS

    .demo {
      border-top: 100px solid #ccc;
      height: 300px;
    }

    @keyframes grow {
      0% { font-size: 0; }
      100% { font-size: 40px; }
    }

    .demo:hover .grows {
      animation-name: grow;
      animation-duration: 3s;
    }

    .demo:hover .growsandstays {
      animation-name: grow;
      animation-duration: 3s;
      animation-fill-mode: forwards;
    }

See [CSS animations](css_animations/using_css_animations) for more examples.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#animation-fill-mode">CSS Animations Level 1<br />
<span class="small">The definition of 'animation-fill-mode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`animation-fill-mode`

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

5

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

4

4.0

1.0

## See also

- [Using CSS animations](css_animations/using_css_animations)
- JavaScript [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent) API

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/animation-fill-mode</a>
