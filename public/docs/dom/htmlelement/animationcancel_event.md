# HTMLElement: animationcancel event

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `animationcancel` event is fired when a [CSS Animation](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations) unexpectedly aborts. In other words, any time it stops running without sending an [`animationend`](animationend_event) event. This might happen when the [`animation-name`](https://developer.mozilla.org/en-US/docs/Web/CSS/animation-name) is changed such that the animation is removed, or when the animating node is hidden using CSS. Therefore, either directly or because any of its containing nodes are hidden.

An event handler for this event can be added by setting the [`onanimationcancel`](../globaleventhandlers/onanimationcancel) property, or using [`addEventListener()`](../eventtarget/addeventlistener).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../animationevent"><code>AnimationEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onanimationcancel"><code>onanimationcancel</code></a></td></tr></tbody></table>

## Examples

This code gets an element that's currently being animated and adds a listener to the `animationcancel` event. It then sets the element's [`display`](https://developer.mozilla.org/en-US/docs/Web/CSS/display) property to `none`, which will trigger the `animationcancel` event.

    const animated = document.querySelector('.animated');

    animated.addEventListener('animationcancel', () => {
      console.log('Animation canceled');
    });

    animated.style.display = 'none';

The same, but using the [`onanimationcancel`](../globaleventhandlers/onanimationcancel) property instead of `addEventListener()`:

    const animated = document.querySelector('.animated');
    animated.onanimationcancel = () => {
      console.log('Animation canceled');
    };

    animated.style.display = 'none';

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/#eventdef-animationevent-animationcancel">CSS Animations Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`animationcancel_event`

No

No

54

No

No

13.1

12

No

No

54

No

13.4

12

No

## See also

- [CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations)
- [Using CSS Animations](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Animations/Using_CSS_animations)
- [`AnimationEvent`](../animationevent)
- Related events: [`animationstart`](animationstart_event), [`animationend`](animationend_event), [`animationiteration`](animationiteration_event)
- This event on [`Document`](../document) targets: [`animationcancel`](../document/animationcancel_event)
- This event on [`Window`](../window) targets: [`animationcancel`](../window/animationcancel_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationcancel_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/animationcancel_event</a>
