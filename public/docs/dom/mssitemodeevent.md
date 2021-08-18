# MSSiteModeEvent

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

`MSSiteModeEvent` provides event properties that are specific to pinned site events.

This proprietary method is specific to Internet Explorer and Microsoft Edge.

### DOM Information

_Inheritance Hierarchy_

[Event](event)

MSSiteModeEvent

### Methods

<table><thead><tr class="header"><th>Method</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>initEvent</code></td><td>Initializes a new generic event that the createEvent method created. <em>*Note that as of Microsoft Edge, the <code>createEvent()/initEvent()</code> constructor pattern for synthetic events is deprecated.</em></td></tr><tr class="even"><td><code>preventDefault</code></td><td>Cancels the default action of an event.</td></tr><tr class="odd"><td><code>stopImmediatePropagation</code></td><td>Prevents any further propagation of an event.</td></tr><tr class="even"><td><code>stopPropagation</code></td><td>Prevents propagation of an event beyond the current target.</td></tr></tbody></table>

### Properties

<table><thead><tr class="header"><th>Property</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>actionURL</code></td><td>Gets the URL of a Jump List item that is removed. <em>*This property is not supported for Windows Store apps using JavaScript.</em></td></tr><tr class="even"><td><code>bubbles</code></td><td>Gets a value that indicates whether an event propagates up from the event target.</td></tr><tr class="odd"><td><code>buttonID</code></td><td>Gets the Thumbnail Toolbar button ID that is clicked. <em>*This property is not supported for Windows Store apps using JavaScript.</em></td></tr><tr class="even"><td><code>cancelable</code></td><td>Gets a value that indicates whether you can cancel an event's default action.</td></tr><tr class="odd"><td><code>cancelBubble</code></td><td>Gets or sets a value that indicates whether an event should be stopped from propagating up from the current target.</td></tr><tr class="even"><td><code>currentTarget</code></td><td>Gets the event target that is currently being processed.</td></tr><tr class="odd"><td><code>defaultPrevented</code></td><td>Gets a value that indicates whether the default action should be canceled.</td></tr><tr class="even"><td><code>eventPhase</code></td><td>Gets the event phase that is being evaluated.</td></tr><tr class="odd"><td><code>isTrusted</code></td><td>Gets a value that indicates whether a trusted event source created an event.</td></tr><tr class="even"><td><code>srcElement</code></td><td>Gets the element that the event was originally dispatched to. Compare to <em>target</em>.</td></tr><tr class="odd"><td><code>target</code></td><td>Gets the element that is the target of the event.</td></tr><tr class="even"><td><code>timeStamp</code></td><td>Gets the time, in milliseconds, when an event occurred.</td></tr><tr class="odd"><td><code>type</code></td><td>Gets the name of an event.</td></tr></tbody></table>

Although this event inherits from the [Event](event) object, it cannot be created by using `createEvent`.

## Example

    interface MSSiteModeEvent extends Event {
        buttonID: number;
        actionURL: string;
    }
    declare var MSSiteModeEvent: {
        prototype: MSSiteModeEvent;
        new(): MSSiteModeEvent;
    }

## See also

- [Microsoft API extensions](microsoft_extensions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MSSiteModeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MSSiteModeEvent</a>
