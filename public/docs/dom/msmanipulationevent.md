MSManipulationEvent
===================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`MSManipulationEvent` provides contextual information when contact is made to the screen and an element is manipulated.

This proprietary method is specific to Internet Explorer.

### Events

`MSManipulationStateChanged`: Event fires when the state of an element being manipulated has changed.

### Methods

[`MSManipulationEvent.initMSManipulationEvent()`](msmanipulationevent/initmsmanipulationevent): Used to create a manipulation event that can be called from JavaScript.

### Properties

<table><thead><tr class="header"><th>Property</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>currentState</code><span class="badge inline readonly">Read only </span></td><td>Returns the current state of a manipulation event.</td></tr><tr class="even"><td><code>inertiaDestinationX</code><span class="badge inline readonly">Read only </span></td><td>Represents the predicted horizontal scroll offset after the inertia phase completes.</td></tr><tr class="odd"><td><code>inertiaDestinationY</code><span class="badge inline readonly">Read only </span></td><td>Represents the predicted vertical scroll offset after the inertia phase completes.</td></tr><tr class="even"><td><code>lastState</code><span class="badge inline readonly">Read only </span></td><td>Returns the last state after a manipulation change event.</td></tr></tbody></table>

Example
-------

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

-   [`TouchEvent`](touchevent)
-   `MSManipulationStateChanged`
-   [Microsoft API extensions](microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MSManipulationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MSManipulationEvent</a>
