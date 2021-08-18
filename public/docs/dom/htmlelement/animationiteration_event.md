HTMLElement: animationiteration event
=====================================

The `animationiteration` event is fired when an iteration of a [CSS Animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) ends, and another one begins. This event does not occur at the same time as the [`animationend`](animationend_event) event, and therefore does not occur for animations with an `animation-iteration-count` of one.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../animationevent"><code>AnimationEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onanimationiteration"><code>onanimationiteration</code></a></td></tr></tbody></table>

Examples
--------

This code uses `animationiteration` to keep track of the number of iterations an animation has completed:

    const animated = document.querySelector('.animated');

    let iterationCount = 0;

    animated.addEventListener('animationiteration', () => {
      iterationCount++;
      console.log(`Animation iteration count: ${iterationCount}`);
    });

The same, but using the `onanimationiteration` event handler property:

    const animated = document.querySelector('.animated');

    let iterationCount = 0;

    animated.onanimationiteration = () => {
      iterationCount++;
      console.log(`Animation iteration count: ${iterationCount}`);
    };

### Live example

#### HTML

    <div class="animation-example">
        <div class="container">
            <p class="animation">You chose a cold night to visit our planet.</p>
        </div>
        <button class="activate" type="button">Activate animation</button>
        <div class="event-log"></div>
    </div>

#### CSS

    .container {
      height: 3rem;
    }

    .event-log {
      width: 25rem;
      height: 2rem;
      border: 1px solid black;
      margin: 0.2rem;
      padding: 0.2rem;
    }

    .animation.active {
      animation-duration: 2s;
      animation-name: slidein;
      animation-iteration-count: 2;
    }

    @keyframes slidein {
      from {
        transform: translateX(100%) scaleX(3);
      }
      to {
        transform: translateX(0) scaleX(1);
      }
    }

#### JS

    const animation = document.querySelector('p.animation');
    const animationEventLog = document.querySelector('.animation-example>.event-log');
    const applyAnimation = document.querySelector('.animation-example>button.activate');
    let iterationCount = 0;

    animation.addEventListener('animationstart', () => {
      animationEventLog.textContent = `${animationEventLog.textContent}'animation started' `;
    });

    animation.addEventListener('animationiteration', () => {
      iterationCount++;
      animationEventLog.textContent = `${animationEventLog.textContent}'animation iterations: ${iterationCount}' `;
    });

    animation.addEventListener('animationend', () => {
      animationEventLog.textContent = `${animationEventLog.textContent}'animation ended'`;
      animation.classList.remove('active');
      applyAnimation.textContent = "Activate animation";
    });

    animation.addEventListener('animationcancel', () => {
      animationEventLog.textContent = `${animationEventLog.textContent}'animation canceled'`;
    });

    applyAnimation.addEventListener('click', () => {
      animation.classList.toggle('active');
      animationEventLog.textContent = '';
      iterationCount = 0;
      let active = animation.classList.contains('active');
      if (active) {
        applyAnimation.textContent = "Cancel animation";
      } else {
        applyAnimation.textContent = "Activate animation";
      }
    });

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#eventdef-animationevent-animationiteration">CSS Animations Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

Browser compatibility
---------------------

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

`animationiteration_event`

43

12

51

10

30

9

43

43

51

30

9

4.0

See also
--------

-   [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
-   [Using CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
-   [`AnimationEvent`](../animationevent)
-   Related events: [`animationstart`](animationstart_event), [`animationend`](animationend_event), [`animationcancel`](animationcancel_event)
-   This event on [`Document`](../document) targets: [`animationiteration`](../document/animationiteration_event)
-   This event on [`Window`](../window) targets: [`animationiteration`](../window/animationiteration_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationiteration_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationiteration_event</a>
