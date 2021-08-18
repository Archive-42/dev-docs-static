# transition-timing-function

The `transition-timing-function` CSS property sets how intermediate values are calculated for CSS properties being affected by a [transition effect](css_transitions/using_css_transitions).

This, in essence, lets you establish an acceleration curve so that the speed of the transition can vary over its duration.

This acceleration curve is defined using one [`<easing-function>`](easing-function) for each property to be transitioned.

You may specify multiple easing functions; each one will be applied to the corresponding property as specified by the [`transition-property`](transition-property) property, which acts as a `transition-property` list. If there are fewer easing functions specified than in the `transition-property` list, the user agent must calculate which value is used by repeating the list of values until there is one for each transition property. If there are more easing functions, the list is truncated to the right size. In both cases, the CSS declaration stays valid.

## Syntax

    /* Keyword values */
    transition-timing-function: ease;
    transition-timing-function: ease-in;
    transition-timing-function: ease-out;
    transition-timing-function: ease-in-out;
    transition-timing-function: linear;
    transition-timing-function: step-start;
    transition-timing-function: step-end;

    /* Function values */
    transition-timing-function: steps(4, jump-end);
    transition-timing-function: cubic-bezier(0.1, 0.7, 1.0, 0.1);

    /* Steps Function keywords */
    transition-timing-function: steps(4, jump-start);
    transition-timing-function: steps(10, jump-end);
    transition-timing-function: steps(20, jump-none);
    transition-timing-function: steps(5, jump-both);
    transition-timing-function: steps(6, start);
    transition-timing-function: steps(8, end);

    /* Multiple timing functions */
    transition-timing-function: ease, step-start, cubic-bezier(0.1, 0.7, 1.0, 0.1);

    /* Global values */
    transition-timing-function: inherit;
    transition-timing-function: initial;
    transition-timing-function: unset;

### Values

`<easing-function>`  
Each [`<easing-function>`](easing-function) represents the easing function to link to the corresponding property to transition, as defined in [`transition-property`](transition-property).

The non-step keyword values (ease, linear, ease-in-out, etc.) each represent cubic Bézier curve with fixed four point values, with the cubic-bezier() function value allowing for a non-predefined value. The step timing functions divides the input time into a specified number of intervals that are equal in length. It is defined by a number of steps and a step position.

`ease`  
Equal to `cubic-bezier(0.25, 0.1, 0.25, 1.0)`, the default value, increases in velocity towards the middle of the transition, slowing back down at the end.

`linear`  
Equal to `cubic-bezier(0.0, 0.0, 1.0, 1.0)`, transitions at an even speed.

`ease-in`  
Equal to `cubic-bezier(0.42, 0, 1.0, 1.0)`, starts off slowly, with the transition speed increasing until complete.

`ease-out`  
Equal to `cubic-bezier(0, 0, 0.58, 1.0)`, starts transitioning quickly, slowing down the transition continues. •

`ease-in-out`  
Equal to `cubic-bezier(0.42, 0, 0.58, 1.0)`, starts transitioning slowly, speeds up, and then slows down again.

`cubic-bezier(p1, p2, p3, p4)`  
An author defined cubic-Bezier curve, where the p1 and p3 values must be in the range of 0 to 1.

`steps( n, <jumpterm>)`  
Displays the transition along _n stops along the transition, displaying each stop for_ equal lengths of time. For example, if _n_ is 5, there are 5 steps. Whether the transition holds temporarily at 0%, 20%, 40%, 60% and 80%, on the 20%, 40%, 60%, 80% and 100%, or makes 5 stops between the 0% and 100% along the transition, or makes 5 stops including the 0% and 100% marks (on the 0%, 25%, 50%, 75%, and 100%) depends on which of the following jump terms is used:

`jump-start`  
Denotes a left-continuous function, so that the first jump happens when the transition begins;

`jump-end`  
Denotes a right-continuous function, so that the last jump happens when the animation ends;

`jump-none`  
There is no jump on either end. Instead, holding at both the 0% mark and the 100% mark, each for 1/n of the duration

`jump-both`  
Includes pauses at both the 0% and 100% marks, effectively adding a step during the transition time.

`start`  
Same as `jump-start.`

`end`  
Same as `jump-end.`

`step-start`  
Equal to `steps(1, jump-start)`

`step-end`  
Equal to `steps(1, jump-end)`

## Accessibility concerns

Some animations can be helpful such as to guide users to understand what actions are expected, to show relationships within the user interface, and to inform users as to what actions have occurred. Animations can help reduce cognitive load, prevent change blindness, and establish better recall in spatial relationships. However, some animations can be problematic for people with cognitive concerns such as Attention Deficit Hyperactivity Disorder (ADHD) and certain kinds of motion can be a trigger for Vestibular disorders, epilepsy, and migraine and Scotopic sensitivity.

Consider providing a mechanism for pausing or disabling animation, as well as using the [Reduced Motion Media Query](@media/prefers-reduced-motion) to create a complimentary experience for users who have expressed a preference for no animated experiences.

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
       transition-timing-function: ease;
    }
    .easein {
       transition-timing-function: ease-in;
    }
    .easeout {
       transition-timing-function: ease-out;
    }
    .easeinout {
       transition-timing-function: ease-in-out;
    }
    .linear {
       transition-timing-function: linear;
    }
    .cb {
       transition-timing-function: cubic-bezier(0.2,-2,0.8,2);
    }

### Step examples

    .jump-start {
       transition-timing-function: steps(5, jump-start);
    }
    .jump-end {
       transition-timing-function: steps(5, jump-end);
    }
    .jump-none {
       transition-timing-function: steps(5, jump-none);
    }
    .jump-both {
       transition-timing-function: steps(5, jump-both);
    }
    .step-start {
       transition-timing-function: step-start;
    }
    .step-end {
       transition-timing-function: step-end;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/#transition-timing-function-property">CSS Transitions<br />
<span class="small">The definition of 'transition-timing-function' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`transition-timing-function`

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

3.1

≤37

≤37

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

- [Using CSS transitions](css_transitions/using_css_transitions)
- [`transition`](transition)
- [`transition-property`](transition-property)
- [`transition-duration`](transition-duration)
- [`transition-delay`](transition-delay)
- [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transition-timing-function</a>
