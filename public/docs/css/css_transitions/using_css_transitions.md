# Using CSS transitions

**CSS transitions** provide a way to control animation speed when changing CSS properties. Instead of having property changes take effect immediately, you can cause the changes in a property to take place over a period of time. For example, if you change the color of an element from white to black, usually the change is instantaneous. With CSS transitions enabled, changes occur at time intervals that follow an acceleration curve, all of which can be customized.

Animations that involve transitioning between two states are often called _implicit transitions_ as the states in between the start and final states are implicitly defined by the browser.

<img src="data:image/png;base64,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" alt="A CSS transition tells the browser to draw the intermediate states between the initial and final states, showing the user a smooth transitions." width="706" height="204" />

CSS transitions let you decide which properties to animate (by _listing them explicitly_), when the animation will start (by setting a _delay)_, how long the transition will last (by setting a _duration_), and how the transition will run (by defining a _timing function_, e.g. linearly or quick at the beginning, slow at the end).

## Which CSS properties can be transitioned?

The Web author can define which property has to be animated and in which way. This allows the creation of complex transitions. As it doesn't make sense to animate some properties, the [list of animatable properties](../css_animated_properties) is limited to a finite set.

Note: The set of properties that can be animated is changing as the specification develops.

The `auto` value is often a very complex case. The specification recommends not animating from and to `auto`. Some user agents, like those based on Gecko, implement this requirement and others, like those based on WebKit, are less strict. Using animations with `auto` may lead to unpredictable results, depending on the browser and its version, and should be avoided.

## Defining transitions

CSS Transitions are controlled using the shorthand [`transition`](../transition) property. This is the best way to configure transitions, as it makes it easier to avoid out of sync parameters, which can be very frustrating to have to spend lots of time debugging in CSS.

You can control the individual components of the transition with the following sub-properties:

**(Note that these transitions loop infinitely only for the purpose of our examples; CSS `transition`s only visualize a property change from start to finish. If you need visualizations that loop, look into the CSS [`animation`](../animation) property.)**

[`transition-property`](../transition-property)  
Specifies the name or names of the CSS properties to which transitions should be applied. Only properties listed here are animated during transitions; changes to all other properties occur instantaneously as usual.

[`transition-duration`](../transition-duration)  
Specifies the duration over which transitions should occur. You can specify a single duration that applies to all properties during the transition, or multiple values to allow each property to transition over a different period of time.

`transition-duration: 0.5s`

`transition-duration: 1s`

`transition-duration: 2s`

`transition-duration: 4s`

[`transition-timing-function`](../transition-timing-function)  
<img src="data:image/png;base64,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" alt="A graph with the Y axis labeled &#39;Output ratio&#39; and the X axis labeled &#39;Time ratio&#39;. The ranges of the X and Y axis go from 0 at the origin to 1.0, with a middle value of 0.5. A curving arc starts at the origin an ends at X 1.0 Y 1.0, and rapidly climbs, extending past the tip of the Y axis and then curving back down to the end point." width="249" height="332" />Specifies a function to define how intermediate values for properties are computed. _Timing functions_ determine how intermediate values of the transition are calculated. Most [timing functions](../easing-function) can be specified by providing the graph of the corresponding function, as defined by four points defining a cubic bezier. You can also choose easing from [Easing Functions Cheat Sheet](https://easings.net/).

`transition-timing-function: ease`

`transition-timing-function: linear`

`transition-timing-function: step-end`

`transition-timing-function: steps(4, end)`

[`transition-delay`](../transition-delay)  
Defines how long to wait between the time a property is changed and the transition actually begins.

`transition-delay: 0.5s`

`transition-delay: 1s`

`transition-delay: 2s`

`transition-delay: 4s`

The shorthand CSS syntax is written as follows:

    div {
        transition: <property> <duration> <timing-function> <delay>;
    }

## Examples

### Simple example

This example performs a four-second font size transition with a two-second delay between the time the user mouses over the element and the beginning of the animation effect:

    #delay {
      font-size: 14px;
      transition-property: font-size;
      transition-duration: 4s;
      transition-delay: 2s;
    }

    #delay:hover {
      font-size: 36px;
    }

### Multiple animated properties example

#### CSS Content

    .box {
        border-style: solid;
        border-width: 1px;
        display: block;
        width: 100px;
        height: 100px;
        background-color: #0000FF;
        transition: width 2s, height 2s, background-color 2s, transform 2s;
    }

    .box:hover {
        background-color: #FFCCCC;
        width: 200px;
        height: 200px;
        transform: rotate(180deg);
    }

### When property value lists are of different lengths

If any property's list of values is shorter than the others, its values are repeated to make them match. For example:

    div {
      transition-property: opacity, left, top, height;
      transition-duration: 3s, 5s;
    }

This is treated as if it were:

    div {
      transition-property: opacity, left, top, height;
      transition-duration: 3s, 5s, 3s, 5s;
    }

Similarly, if any property's value list is longer than that for [`transition-property`](../transition-property), it's truncated, so if you have the following CSS:

    div {
      transition-property: opacity, left;
      transition-duration: 3s, 5s, 2s, 1s;
    }

This gets interpreted as:

    div {
      transition-property: opacity, left;
      transition-duration: 3s, 5s;
    }

### Using transitions when highlighting menus

A common use of CSS is to highlight items in a menu as the user hovers the mouse cursor over them. It's easy to use transitions to make the effect even more attractive.

Before we look at code snippets, you might want to take a look at the [live demo](https://codepen.io/anon/pen/WOEpva) (assuming your browser supports transitions).

First, we set up the menu using HTML:

    <nav>
      <a href="#">Home</a>
      <a href="#">About</a>
      <a href="#">Contact Us</a>
      <a href="#">Links</a>
    </nav>

Then we build the CSS to implement the look and feel of our menu. The relevant portions are shown here:

    a {
      color: #fff;
      background-color: #333;
      transition: all 1s ease-out;
    }

    a:hover,
    a:focus {
      color: #333;
      background-color: #fff;
    }

This CSS establishes the look of the menu, with the background and text colors both changing when the element is in its [`:hover`](../:hover) and [`:focus`](../:focus) states.

## JavaScript examples

Care should be taken when using a transition immediately after:

- adding the element to the DOM using `.appendChild()`
- removing an element's `display: none;` property.

This is treated as if the initial state had never occurred and the element was always in its final state. The easy way to overcome this limitation is to apply a `window.setTimeout()` of a handful of milliseconds before changing the CSS property you intend to transition to.

### Using transitions to make JavaScript functionality smooth

Transitions are a great tool to make things look much smoother without having to do anything to your JavaScript functionality. Take the following example.

    <p>Click anywhere to move the ball</p>
    <div id="foo" class="ball"></div>

Using JavaScript you can make the effect of moving the ball to a certain position happen:

    var f = document.getElementById('foo');
    document.addEventListener('click', function(ev){
        f.style.transform = 'translateY('+(ev.clientY-25)+'px)';
        f.style.transform += 'translateX('+(ev.clientX-25)+'px)';
    },false);

With CSS you can make it smooth without any extra effort. Add a transition to the element and any change will happen smoothly:

    .ball {
      border-radius: 25px;
      width: 50px;
      height: 50px;
      background: #c00;
      position: absolute;
      top: 0;
      left: 0;
      transition: transform 1s;
    }

### Detecting the start and completion of a transition

You can use the `transitionend` event to detect that an animation has finished running. This is a [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent) object, which has two added properties beyond a typical [`Event`](https://developer.mozilla.org/en-US/docs/Web/API/Event) object:

`propertyName`  
A string indicating the name of the CSS property whose transition completed.

`elapsedTime`  
A float indicating the number of seconds the transition had been running at the time the event fired. This value isn't affected by the value of [`transition-delay`](../transition-delay).

As usual, you can use the [`addEventListener()`](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) method to monitor for this event:

    el.addEventListener("transitionend", updateTransition, true);

You detect the beginning of a transition using `transitionrun` (fires before any delay) and `transitionstart` (fires after any delay), in the same kind of fashion:

    el.addEventListener("transitionrun", signalStart, true);
    el.addEventListener("transitionstart", signalStart, true);

**Note**: The `transitionend` event doesn't fire if the transition is aborted before the transition is completed because either the element is made [`display`](../display)`: none` or the animating property's value is changed.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transitions/">CSS Transitions</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

## See also

- The [`TransitionEvent`](https://developer.mozilla.org/en-US/docs/Web/API/TransitionEvent) interface and the `transitionend` event.
- [Using CSS animations](../css_animations/using_css_animations)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions</a>
