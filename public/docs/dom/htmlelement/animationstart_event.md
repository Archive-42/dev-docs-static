# HTMLElement: animationstart event

The `animationstart` event is fired when a [CSS Animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has started. If there is an [`animation-delay`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-delay), this event will fire once the delay period has expired. A negative delay will cause the event to fire with an [`elapsedTime`](../animationevent/elapsedtime) equal to the absolute value of the delay (and, correspondingly, the animation will begin playing at that time index into the sequence).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../animationevent"><code>AnimationEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onanimationstart"><code>onanimationstart</code></a></td></tr></tbody></table>

## Examples

This listens for the `animationstart` event and logs a message when it is fired:

    const animated = document.querySelector('.animated');

    animated.addEventListener('animationstart', () => {
      console.log('Animation started');
    });

The same, but using `onanimationstart`:

    const animated = document.querySelector('.animated');

    animated.onanimationstart = () => {
      console.log('Animation started');
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

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#eventdef-animationevent-animationstart">CSS Animations Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`animationstart_event`

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

## See also

- [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
- [Using CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- [`AnimationEvent`](../animationevent)
- Related events: [`animationend`](animationend_event), [`animationiteration`](animationiteration_event), [`animationcancel`](animationcancel_event)
- This event on [`Document`](../document) targets: [`animationstart`](../document/animationstart_event)
- This event on [`Window`](../window) targets: [`animationstart`](../window/animationstart_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationstart_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationstart_event</a>
