# animation

The `animation` [shorthand](shorthand_properties) [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property applies an animation between styles. It is a shorthand for [`animation-name`](animation-name), [`animation-duration`](animation-duration), [`animation-timing-function`](animation-timing-function), [`animation-delay`](animation-delay), [`animation-iteration-count`](animation-iteration-count), [`animation-direction`](animation-direction), [`animation-fill-mode`](animation-fill-mode), and [`animation-play-state`](animation-play-state).

    /* @keyframes duration | easing-function | delay |
    iteration-count | direction | fill-mode | play-state | name */
    animation: 3s ease-in 1s 2 reverse both paused slidein;

    /* @keyframes name | duration | easing-function | delay */
    animation: slidein 3s linear 1s;

    /* @keyframes name | duration */
    animation: slidein 3s;

A [description of which properties are animatable](css_transitions/using_css_transitions#which_css_properties_are_animatable) is available; it's worth noting that this description is also valid for [CSS transitions](css_transitions/using_css_transitions).

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`animation-delay`](animation-delay)
- [`animation-direction`](animation-direction)
- [`animation-duration`](animation-duration)
- [`animation-fill-mode`](animation-fill-mode)
- [`animation-iteration-count`](animation-iteration-count)
- [`animation-name`](animation-name)
- [`animation-play-state`](animation-play-state)
- [`animation-timing-function`](animation-timing-function)

## Syntax

The `animation` property is specified as one or more single animations, separated by commas.

Each individual animation is specified as:

- zero or one occurrences of the following values:
  - <span class="page-not-created">`<single-transition-easing-function>`</span>
  - [`<single-animation-iteration-count>`](#%3Csingle-animation-iteration-count%3E)
  - [`<single-animation-direction>`](#%3Csingle-animation-direction%3E)
  - [`<single-animation-fill-mode>`](#%3Csingle-animation-fill-mode%3E)
  - [`<single-animation-play-state>`](#%3Csingle-animation-play-state%3E)
- an optional name for the animation, which may be `none`, a [`<custom-ident>`](custom-ident), or a [`<string>`](string)
- zero, one, or two [`<time>`](time) values

The order of values within each animation definition is important: the first value that can be parsed as a [`<time>`](time) is assigned to the [`animation-duration`](animation-duration), and the second one is assigned to [`animation-delay`](animation-delay).

The order within each animation definition is also important for distinguishing [`animation-name`](animation-name) values from other keywords. When parsed, keywords that are valid for properties other than [`animation-name`](animation-name), and whose values were not found earlier in the shorthand, must be accepted for those properties rather than for [`animation-name`](animation-name). Furthermore, when serialized, default values of other properties must be output in at least the cases necessary to distinguish an [`animation-name`](animation-name) that could be a value of another property, and may be output in additional cases.

### Values

`<single-animation-iteration-count>`  
The number of times the animation is played. The value must be one of those available in [`animation-iteration-count`](animation-iteration-count).

`<single-animation-direction>`  
The direction in which the animation is played. The value must be one of those available in [`animation-direction`](animation-direction).

`<single-animation-fill-mode>`  
Determines how styles should be applied to the animation's target before and after its execution. The value must be one of those available in [`animation-fill-mode`](animation-fill-mode).

`<single-animation-play-state>`  
Determines whether the animation is playing or not. The value must be one of those available in [`animation-play-state`](animation-play-state).

## Accessibility concerns

Blinking and flashing animation can be problematic for people with cognitive concerns such as Attention Deficit Hyperactivity Disorder (ADHD). Additionally, certain kinds of motion can be a trigger for Vestibular disorders, epilepsy, and migraine and Scotopic sensitivity.

Consider providing a mechanism for pausing or disabling animation, as well as using the [Reduced Motion Media Query](@media/prefers-reduced-motion) to create a complimentary experience for users who have expressed a preference for no animated experiences.

- [Designing Safer Web Animation For Motion Sensitivity · An A List Apart Article](https://alistapart.com/article/designing-safer-web-animation-for-motion-sensitivity)
- [An Introduction to the Reduced Motion Media Query | CSS-Tricks](https://css-tricks.com/introduction-reduced-motion-media-query/)
- [Responsive Design for Motion | WebKit](https://webkit.org/blog/7551/responsive-design-for-motion/)
- [MDN Understanding WCAG, Guideline 2.2 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Operable#guideline_2.2_%e2%80%94_enough_time_provide_users_enough_time_to_read_and_use_content)
- [Understanding Success Criterion 2.2.2 | W3C Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/time-limits-pause.html)

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="animation-name"><code>animation-name</code></a>: <code>none</code></li><li><a href="animation-duration"><code>animation-duration</code></a>: <code>0s</code></li><li><a href="animation-timing-function"><code>animation-timing-function</code></a>: <code>ease</code></li><li><a href="animation-delay"><code>animation-delay</code></a>: <code>0s</code></li><li><a href="animation-iteration-count"><code>animation-iteration-count</code></a>: <code>1</code></li><li><a href="animation-direction"><code>animation-direction</code></a>: <code>normal</code></li><li><a href="animation-fill-mode"><code>animation-fill-mode</code></a>: <code>none</code></li><li><a href="animation-play-state"><code>animation-play-state</code></a>: <code>running</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements, <a href="::before"><code>::before</code></a> and <a href="::after"><code>::after</code></a> <a href="pseudo-elements">pseudo-elements</a></td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="animation-name"><code>animation-name</code></a>: as specified</li><li><a href="animation-duration"><code>animation-duration</code></a>: as specified</li><li><a href="animation-timing-function"><code>animation-timing-function</code></a>: as specified</li><li><a href="animation-delay"><code>animation-delay</code></a>: as specified</li><li><a href="animation-direction"><code>animation-direction</code></a>: as specified</li><li><a href="animation-iteration-count"><code>animation-iteration-count</code></a>: as specified</li><li><a href="animation-fill-mode"><code>animation-fill-mode</code></a>: as specified</li><li><a href="animation-play-state"><code>animation-play-state</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <single-animation>#where
    <single-animation> = <time> || <easing-function> || <time> || <single-animation-iteration-count> || <single-animation-direction> || <single-animation-fill-mode> || <single-animation-play-state> || [ none | <keyframes-name> ]where
    <easing-function> = linear | <cubic-bezier-timing-function> | <step-timing-function>
    <single-animation-iteration-count> = infinite | <number>
    <single-animation-direction> = normal | reverse | alternate | alternate-reverse
    <single-animation-fill-mode> = none | forwards | backwards | both
    <single-animation-play-state> = running | paused
    <keyframes-name> = <custom-ident> | <string>where
    <cubic-bezier-timing-function> = ease | ease-in | ease-out | ease-in-out | cubic-bezier([0,1]>, <number>, [0,1]>, <number>)
    <step-timing-function> = step-start | step-end | steps(<integer>[, <step-position>]?)where
    <step-position> = jump-start | jump-end | jump-none | jump-both | start | end

## Examples

### Cylon Eye

    <div class="view_port">
      <div class="polling_message">
        Listening for dispatches
      </div>
      <div class="cylon_eye"></div>
    </div>

    .polling_message {
      color: white;
      float: left;
      margin-right: 2%;
    }

    .view_port {
      background-color: black;
      height: 25px;
      width: 100%;
      overflow: hidden;
    }

    .cylon_eye {
      background-color: red;
      background-image: linear-gradient(to right,
          rgba(0, 0, 0, .9) 25%,
          rgba(0, 0, 0, .1) 50%,
          rgba(0, 0, 0, .9) 75%);
      color: white;
      height: 100%;
      width: 20%;

      -webkit-animation: 4s linear 0s infinite alternate move_eye;
              animation: 4s linear 0s infinite alternate move_eye;
    }

    @-webkit-keyframes move_eye { from { margin-left: -20%; } to { margin-left: 100%; }  }
            @keyframes move_eye { from { margin-left: -20%; } to { margin-left: 100%; }  }

See [Using CSS animations](css_animations/using_css_animations#examples) for additional examples.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#animation">CSS Animations Level 1<br />
<span class="small">The definition of 'animation' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`animation`

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

2

The [`animation-fill-mode`](https://developer.mozilla.org/docs/Web/CSS/animation-fill-mode) property is not supported in Android browsers below 2.3.

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

### Quantum CSS notes

- Gecko has a bug whereby when you animate an offscreen element onscreen but specify a delay, Gecko does not repaint on some platforms, e.g. Windows ([bug 1383239](https://bugzilla.mozilla.org/show_bug.cgi?id=1383239)). This has been fixed in Firefox's new parallel CSS engine (also known as [Quantum CSS](https://wiki.mozilla.org/Quantum) or [Stylo](https://wiki.mozilla.org/Quantum/Stylo), planned for release in Firefox 57).
- Another Gecko bug means that [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) elements can't be made open by default using the `open` attribute if they have an animation active on them ([bug 1382124](https://bugzilla.mozilla.org/show_bug.cgi?id=1382124)). Quantum CSS fixes this.
- A further bug means that animations using em units are not affected by changes to the [`font-size`](font-size) on the animated element's parent, whereas they should be ([bug 1254424](https://bugzilla.mozilla.org/show_bug.cgi?id=1254424)). Quantum CSS fixes this.

## See also

- [Using CSS animations](css_animations/using_css_animations)
- JavaScript [`AnimationEvent`](https://developer.mozilla.org/en-US/docs/Web/API/AnimationEvent) API

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/animation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/animation</a>
