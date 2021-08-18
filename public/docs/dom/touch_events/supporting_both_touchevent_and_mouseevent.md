Supporting both TouchEvent and MouseEvent
=========================================

The [`touch`](../touch_events) interfaces enable applications to create enhanced user experiences on touch enabled devices. However, the reality is the vast majority of today's web content is designed only to work with mouse input. Consequently, even if a browser supports touch, the browser must still *emulate* mouse events so content that assumes mouse-only input will work *as is* without direct modification.

Ideally, a touch-based application does not need to explicitly address mouse input. However, because the browser must emulate mouse events, there may be some interaction issues that need to be handled. Below are some details about the interaction and the ramifications for application developers.

Event firing
------------

The touch events standard defines a few browser requirements regarding touch and mouse interaction (see the [*Interaction with Mouse Events and click*](https://w3c.github.io/touch-events/#mouse-events) section for details), noting *the browser may fire both touch events and mouse events in response to the same user input*. This section describes the requirement that may affect an application.

If the browser fires both touch and mouse events because of a single user input, the browser *must* fire a `touchstart` before any mouse events. Consequently, if an application does not want mouse events fired on a specific touch [`target`](../touch/target) element, the element's touch event handlers should call [`preventDefault()`](../event/preventdefault) and no additional mouse events will be dispatched.

Here is a code snippet of the `touchmove` event handler calling `preventDefault()`.

    // touchmove handler
    function process_touchmove(ev) {
      // Call preventDefault() to prevent any further handling
      ev.preventDefault();
    }

Event order
-----------

Although the specific ordering of touch and mouse events is implementation-defined, the standard indicates the following order is *typical:* for single input:

-   `touchstart`
-   Zero or more `touchmove` events, depending on movement of the finger(s)
-   `touchend`
-   `mousemove`
-   `mousedown`
-   `mouseup`
-   `click`

If the `touchstart`, `touchmove` or `touchend` event is canceled during an interaction, no mouse or click events will be fired, and the resulting sequence of events would just be:

-   `touchstart`
-   Zero or more `touchmove` events, depending on movement of the finger(s)
-   `touchend`

Community
---------

-   [Touch Events Community Group](https://github.com/w3c/touch-events)
-   [Mail list](https://lists.w3.org/Archives/Public/public-touchevents/)
-   [W3C \#touchevents IRC channel](irc://irc.w3.org:6667/)

Related topics and resources
----------------------------

-   [Touch Events Overview](../touch_events)
-   [Using Touch Events](using_touch_events)
-   [Touch and Mouse (Together Again for the First Time)](https://www.html5rocks.com/en/mobile/touchandmouse/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Touch_events/Supporting_both_TouchEvent_and_MouseEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Touch_events/Supporting_both_TouchEvent_and_MouseEvent</a>
