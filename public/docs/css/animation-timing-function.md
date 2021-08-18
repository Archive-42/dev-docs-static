# animation-timing-function

The `animation-timing-function` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how an animation progresses through the duration of each cycle.

It is often convenient to use the shorthand property [`animation`](animation) to set all animation properties at once.

## Syntax

    /* Keyword values */
    animation-timing-function: ease;
    animation-timing-function: ease-in;
    animation-timing-function: ease-out;
    animation-timing-function: ease-in-out;
    animation-timing-function: linear;
    animation-timing-function: step-start;
    animation-timing-function: step-end;

    /* Function values */
    animation-timing-function: cubic-bezier(0.1, 0.7, 1.0, 0.1);
    animation-timing-function: steps(4, end);

    /* Steps Function keywords */
    animation-timing-function: steps(4, jump-start);
    animation-timing-function: steps(10, jump-end);
    animation-timing-function: steps(20, jump-none);
    animation-timing-function: steps(5, jump-both);
    animation-timing-function: steps(6, start);
    animation-timing-function: steps(8, end);

    /* Multiple animations */
    animation-timing-function: ease, step-start, cubic-bezier(0.1, 0.7, 1.0, 0.1);

    /* Global values */
    animation-timing-function: inherit;
    animation-timing-function: initial;
    animation-timing-function: unset;

Timing functions may be specified on individual keyframes in a [@keyframes](@keyframes) rule. If no `animation-timing-function` is specified on a keyframe, the corresponding value of `animation-timing-function` from the element to which the animation is applied is used for that keyframe.

A keyframe's timing function is applied on a property-by-property basis from the keyframe on which it is specified until the next keyframe specifying that property, or until the end of the animation if there is no subsequent keyframe specifying that property. As a result, an `animation-timing-function` specified on the `100%` or `to` keyframe will never be used.

### Values

[`<easing-function>`](easing-function)  
The easing function that corresponds to a given animation, as determined by [`animation-name`](animation-name).

The non-step keyword values (ease, linear, ease-in-out, etc.) each represent cubic Bézier curve with fixed four point values, with the cubic-bezier() function value allowing for a non-predefined value. The step timing functions divides the input time into a specified number of intervals that are equal in length. It is defined by a number of steps and a step position.

`ease`  
Equal to `cubic-bezier(0.25, 0.1, 0.25, 1.0)`, the default value, increases in velocity towards the middle of the animation, slowing back down at the end.

`linear`  
Equal to `cubic-bezier(0.0, 0.0, 1.0, 1.0)`, animates at an even speed.

`ease-in`  
Equal to `cubic-bezier(0.42, 0, 1.0, 1.0)`, starts off slowly, with the speed of the transition of the animating property increasing until complete.

`ease-out`  
Equal to `cubic-bezier(0, 0, 0.58, 1.0)`, starts quickly, slowing down the animation continues. •

`ease-in-out`  
Equal to `cubic-bezier(0.42, 0, 0.58, 1.0)`, with the animating properties slowly transitioning, speeding up, and then slowing down again.

`cubic-bezier(p1, p2, p3, p4)`  
An author defined cubic-bezier curve, where the p1 and p3 values must be in the range of 0 to 1.

`steps(n, <jumpterm>)`  
Displays an animation iteration along _n_ stops along the transition, displaying each stop for equal lengths of time. For example, if _n_ is 5, there are 5 steps. Whether the animation holds temporarily at 0%, 20%, 40%, 60% and 80%, on the 20%, 40%, 60%, 80% and 100%, or makes 5 stops between the 0% and 100% along the animation, or makes 5 stops including the 0% and 100% marks (on the 0%, 25%, 50%, 75%, and 100%) depends on which of the following jump terms is used:

`jump-start`  
Denotes a left-continuous function, so that the first jump happens when the animation begins;

`jump-end`  
Denotes a right-continuous function, so that the last jump happens when the animation ends;

`jump-none`  
There is no jump on either end. Instead, holding at both the 0% mark and the 100% mark, each for 1/n of the duration.

`jump-both`  
Includes pauses at both the 0% and 100% marks, effectively adding a step during the animation iteration.

`start`  
Same as `jump-start`.

`end`  
Same as `jump-end`.

`step-start`  
Equal to `steps(1, jump-start)`

`step-end`  
Equal to `steps(1, jump-end)`

**Note**: When you specify multiple comma-separated values on an `animation-*` property, they will be assigned to the animations specified in the [`animation-name`](animation-name) property in different ways depending on how many there are. For more information, see [Setting multiple animation property values](css_animations/using_css_animations#setting_multiple_animation_property_values).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>ease</code></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <easing-function>#where
    <easing-function> = linear | <cubic-bezier-timing-function> | <step-timing-function>where
    <cubic-bezier-timing-function> = ease | ease-in | ease-out | ease-in-out | cubic-bezier([0,1]>, <number>, [0,1]>, <number>)
    <step-timing-function> = step-start | step-end | steps(<integer>[, <step-position>]?)where
    <step-position> = jump-start | jump-end | jump-none | jump-both | start | end

## Examples

### Cubic-Bezier examples

    .ease {
       animation-timing-function: ease;
    }
    .easein {
       animation-timing-function: ease-in;
    }
    .easeout {
       animation-timing-function: ease-out;
    }
    .easeinout {
       animation-timing-function: ease-in-out;
    }
    .linear {
       animation-timing-function: linear;
    }
    .cb {
       animation-timing-function: cubic-bezier(0.2,-2,0.8,2);
    }

### Step examples

    .jump-start {
       animation-timing-function: steps(5, jump-start);
    }
    .jump-end {
       animation-timing-function: steps(5, jump-end);
    }
    .jump-none {
       animation-timing-function: steps(5, jump-none);
    }
    .jump-both {
       animation-timing-function: steps(5, jump-both);
    }
    .start {
       animation-timing-function: steps(5, start);
    }
    .end {
       animation-timing-function: steps(5, end);
    }
    .step-start {
       animation-timing-function: step-start;
    }
    .step-end {
       animation-timing-function: step-end;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#animation-timing-function">CSS Animations Level 1<br />
<span class="small">The definition of 'animation-timing-function' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`animation-timing-function`

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

`jump`

77

79

65

No

64

14

77

77

65

55

14

12.0

## See also

- [Using CSS animations](css_animations/using_css_animations)
- [`<timing-function>`](easing-function)
- JavaScript [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent) API
- [cubic-bezier.com](https://cubic-bezier.com)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/animation-timing-function</a>
