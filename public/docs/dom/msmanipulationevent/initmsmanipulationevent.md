MSManipulationEvent.initMSManipulationEvent()
=============================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `initMSManipulationEvent` method is used to create a [`MSManipulationEvent`](../msmanipulationevent) that can be called from JavaScript.

This proprietary method is specific to Internet Explorer. Beginning with the Microsoft Edge browser, the [initEvent()](../event/initevent) constructor pattern for synthetic events is deprecated.

### Syntax

    MSManipulationEvent.initMSManipulationEvent(typeArg, canBubbleArg, cancelableArg, viewArg, detailArg, lastState, currentState);

### Parameters

**typeArg** \[in\]

Type: *DOMString*

The type of the event being created.

**canBubbleArg** \[in\]

Type: *boolean*

Indicates whether the event can bubble. When true the event should propagate upward. When false the event does not propagate upward.

**cancelableArg** \[in\]

Type: *boolean*

Indicates whether the event’s default action can be prevented. When true, the default action can be canceled. When false, the default action cannot be canceled.

**viewArg** \[in\]

Type: *AbstractView*

The view in which the event is taking place.

**detailArg** \[in\]

Type: *Integer*

Specifies some detailed information depending upon the event.

**lastState** \[in\]

Type: *Integer*

Indicates the last state of the manipulation event.

**currentState** \[in\]

Type: *Integer*

Indicates the current state of the manipulation event.

### Return value

This method does not return a value.

### Example

    interface MSManipulationEvent extends UIEvent {
        readonly currentState: number;
        readonly inertiaDestinationX: number;
        readonly inertiaDestinationY: number;
        readonly lastState: number;
        initMSManipulationEvent(typeArg: string, canBubbleArg: boolean, cancelableArg: boolean, viewArg: Window, detailArg: number, lastState: number, currentState: number): void;
        readonly MS_MANIPULATION_STATE_ACTIVE: number;
        readonly MS_MANIPULATION_STATE_CANCELLED: number;
        readonly MS_MANIPULATION_STATE_COMMITTED: number;
        readonly MS_MANIPULATION_STATE_DRAGGING: number;
        readonly MS_MANIPULATION_STATE_INERTIA: number;
        readonly MS_MANIPULATION_STATE_PRESELECT: number;
        readonly MS_MANIPULATION_STATE_SELECTING: number;
        readonly MS_MANIPULATION_STATE_STOPPED: number;
    }

See also
--------

-   [MSManipulationEvent](../msmanipulationevent)
-   [Microsoft API extensions](../microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MSManipulationEvent/initMSManipulationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MSManipulationEvent/initMSManipulationEvent</a>
