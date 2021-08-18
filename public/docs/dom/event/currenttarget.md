# Event.currentTarget

The `currentTarget` read-only property of the [`Event`](../event) interface identifies the current target for the event, as the event traverses the DOM. It always refers to the element to which the event handler has been attached, as opposed to [`Event.target`](target), which identifies the element on which the event occurred and which may be its descendant.

## Syntax

    var currentEventTarget = event.currentTarget;

### Value

[`EventTarget`](../eventtarget)

## Examples

`Event.currentTarget` is interesting to use when attaching the same event handler to several elements.

    function hide(e){
      e.currentTarget.style.visibility = 'hidden';
      console.log(e.currentTarget);
      // When this function is used as an event handler: this === e.currentTarget
    }

    var ps = document.getElementsByTagName('p');

    for(var i = 0; i < ps.length; i++){
      // Console: print the clicked <p> element
      ps[i].addEventListener('click', hide, false);
    }
    // Console: print <body>
    document.body.addEventListener('click', hide, false);

    // Click around and make paragraphs disappear

**Note:** The value of `event.currentTarget` is **only** available while the event is being handled. If you `console.log()` the `event` object, storing it in a variable, and _then_ look for the `currentTarget` key in the console, its value will be `null`. Instead, you can either directly `console.log(event.currentTarget)` to be able to view it in the console or use the `debugger` statement, which will pause the execution of your code thus showing you the value of `event.currentTarget`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-currenttarget">DOM<br />
<span class="small">The definition of 'Event.currentTarget' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#dom-event-currenttarget">DOM4<br />
<span class="small">The definition of 'Event.currentTarget' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#dfn-current-event-target">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'current event target' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-Event-currentTarget">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'Event.currentTarget' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`currentTarget`

1

12

1

9

6-9

On Internet Explorer 6 through 8, the event model is different. Event listeners are attached with the non-standard [`EventTarget.attachEvent`](https://developer.mozilla.org/docs/Web/API/EventTarget/attachEvent) method. In this model, there is no equivalent to `event.currentTarget` and `this` is the global object. One solution to emulate the `event.currentTarget` feature is to wrap your handler in a function calling the handler using `Function.prototype.call` with the element as a first argument. This way, `this` will be the expected value.

7

10

1

18

4

10.1

10

1.0

## See also

- [Comparison of Event Targets](comparison_of_event_targets)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/currentTarget" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/currentTarget</a>
