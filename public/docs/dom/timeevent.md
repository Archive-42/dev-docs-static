TimeEvent
=========

The `TimeEvent` interface, a part of [SVG SMIL](https://developer.mozilla.org/en-US/docs/Web/SVG/SVG_animation_with_SMIL) animation, provides specific contextual information associated with Time events.

Properties
----------

 <span class="page-not-created">`TimeEvent.detail`</span> <span class="badge inline readonly">Read only </span>   
Is a `long` that specifies some detail information about the Event, depending on the type of the event. For this event type, indicates the repeat number for the animation.

 <span class="page-not-created">`TimeEvent.view`</span> <span class="badge inline readonly">Read only </span>   
Is a <span class="page-not-created">`WindowProxy`</span> that identifies the Window from which the event was generated.

Methods
-------

 <span class="page-not-created">`initTimeEvent`</span>(DOMString typeArg, AbstractView viewArg, long detailArg)  
The initTimeEvent method is used to initialize the value of a TimeEvent created through the DocumentEvent interface. This method may only be called before the TimeEvent has been dispatched via the dispatchEvent method, though it may be called multiple times during that phase if necessary.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/TimeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/TimeEvent</a>
