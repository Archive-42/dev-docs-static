# HTMLElement: animationend event

The `animationend` event is fired when a [CSS Animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) has completed. If the animation aborts before reaching completion, such as if the element is removed from the DOM or the animation is removed from the element, the `animationend` event is not fired.

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../animationevent"><code>AnimationEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onanimationend"><code>onanimationend</code></a></td></tr></tbody></table>

## Examples

This example gets an element that's being animated and listens for the `animationend` event:

    const animated = document.querySelector('.animated');

    animated.addEventListener('animationend', () => {
      console.log('Animation ended');
    });

The same, but using the `onanimationend` event handler property:

    const animated = document.querySelector('.animated');

    animated.onanimationend = () => {
      console.log('Animation ended');
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
      margin: .2rem;
      padding: .2rem;
    }

    .animation.active {
      animation-duration: 2s;
      animation-name: slidein;
      animation-iteration-count: 2;
    }

    @keyframes slidein {
      from {
        margin-left: 100%;
        width: 300%;
      }

      to {
        margin-left: 0%;
        width: 100%;
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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#eventdef-animationevent-animationend">CSS Animations Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`animationend_event`

43

12

Yes

10

30

9

43

43

Yes

30

9

4.0

## See also

- [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
- [Using CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- [`AnimationEvent`](../animationevent)
- Related events: [`animationstart`](animationstart_event), [`animationcancel`](animationcancel_event), [`animationiteration`](animationiteration_event)
- This event on [`Document`](../document) targets: [`animationend`](../document/animationend_event)
- This event on [`Window`](../window) targets: [`animationend`](../window/animationend_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationend_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationend_event</a>
