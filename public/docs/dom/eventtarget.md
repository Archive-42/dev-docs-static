EventTarget
===========

`EventTarget` is a DOM interface implemented by objects that can receive events and may have listeners for them.

[`Element`](element), [`Document`](document), and [`Window`](window) are the most common event targets, but other objects can be event targets, too. For example [`XMLHttpRequest`](xmlhttprequest), [`AudioNode`](audionode), [`AudioContext`](audiocontext), and others.

Many event targets (including elements, documents, and windows) also support setting [event handlers](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) via `onevent` properties and attributes.

Constructor
-----------

[`EventTarget()`](eventtarget/eventtarget)  
Creates a new `EventTarget` object instance.

Methods
-------

[`EventTarget.addEventListener()`](eventtarget/addeventlistener)  
Registers an event handler of a specific event type on the `EventTarget`.

[`EventTarget.removeEventListener()`](eventtarget/removeeventlistener)  
Removes an event listener from the `EventTarget`.

[`EventTarget.dispatchEvent()`](eventtarget/dispatchevent)  
Dispatches an event to this `EventTarget`.

Example
-------

### Simple implementation of EventTarget

    var EventTarget = function() {
      this.listeners = {};
    };

    EventTarget.prototype.listeners = null;
    EventTarget.prototype.addEventListener = function(type, callback) {
      if (!(type in this.listeners)) {
        this.listeners[type] = [];
      }
      this.listeners[type].push(callback);
    };

    EventTarget.prototype.removeEventListener = function(type, callback) {
      if (!(type in this.listeners)) {
        return;
      }
      var stack = this.listeners[type];
      for (var i = 0, l = stack.length; i < l; i++) {
        if (stack[i] === callback){
          stack.splice(i, 1);
          return;
        }
      }
    };

    EventTarget.prototype.dispatchEvent = function(event) {
      if (!(event.type in this.listeners)) {
        return true;
      }
      var stack = this.listeners[event.type].slice();

      for (var i = 0, l = stack.length; i < l; i++) {
        stack[i].call(this, event);
      }
      return !event.defaultPrevented;
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-eventtarget">DOM<br />
<span class="small">The definition of 'EventTarget' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/DOM3-Events.html#interface-EventTarget">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'EventTarget' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>A few parameters are now optional (<code>listener</code>), or accepts the <code>null</code> value (<code>useCapture</code>).</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.htmlevents.html#Events-EventTarget">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'EventTarget' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`EventTarget`

1

12

1

6

7

1

`window.EventTarget` did not exist on versions of Safari before 10.1.

1

18

4

10.1

1

`window.EventTarget` did not exist on versions of Safari iOS before 10.3.

1.0

`EventTarget`

64

79

59

No

51

14

64

64

59

47

14

9.0

`addEventListener`

1

Before Chrome 49, the `type` and `listener` parameters were optional.

12

1

9

6-11

Older versions of IE supported an equivalent, proprietary `EventTarget.attachEvent()` method.

7

1

1

Before Chrome 49, the `type` and `listener` parameters were optional.

18

Before Chrome 49, the `type` and `listener` parameters were optional.

4

10.1

1

1.0

Before Samsung Internet 5.0, the `type` and `listener` parameters were optional.

`dispatchEvent`

4

12

2

9

6-11

Older versions of IE supported an equivalent, proprietary `EventTarget.fireEvent()` method.

9

3.2

4

18

4

10.1

3

1.0

`removeEventListener`

1

12

1

9

6-11

Older versions of IE supported an equivalent, proprietary `EventTarget.detachEvent()` method.

7

1

1

18

4

10.1

1

1.0

See also
--------

-   [Event reference](https://developer.mozilla.org/en-US/docs/Web/Events) - the events available in the platform.
-   [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
-   [`Event`](event) interface

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventTarget" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventTarget</a>
