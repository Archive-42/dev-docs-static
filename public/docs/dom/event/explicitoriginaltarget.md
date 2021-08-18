# Event.explicitOriginalTarget

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The explicit original target of the event. (Mozilla-specific)

If the event was [retargeted](https://developer.mozilla.org/en-US/docs/DOM/event_retargeting) for some reason other than an [anonymous boundary crossing](https://developer.mozilla.org/en-US/docs/DOM/anonymous_boundary_crossing), this will be set to the target before the retargeting occurs. For example, mouse events are retargeted to their parent node when they happen over text nodes (see [bug 185889](https://bugzilla.mozilla.org/show_bug.cgi?id=185889)), and in that case `currentTarget` will show the parent and `explicitOriginalTarget` will show the text node.

`explicitOriginalTarget` differs from `originalTarget` in that it will never contain [anonymous content](https://developer.mozilla.org/en-US/docs/DOM/anonymous_content).

## Example

This property can be used with `<command>` to get the event details of the original object calling the command.

    function myCommand(ev) {
      alert(ev.explicitOriginalTarget.nodeName); // returns 'menuitem'
    }

    <xul:command id="my-cmd-anAction" oncommand="myCommand(event);"/>

    <xul:menulist>
      <xul:menupopup>
        <xul:menuitem label="Get my element name!" command="my-cmd-anAction"/>
      </xul:menupopup>
    </menulist>

## Specifications

_This is a Mozilla-specific property._ Defined in `/dom/public/idl/events/nsIDOMNSEvent.idl`

This event property is **not defined** in the [W3.org DOM Level 2 Events](https://www.w3.org/TR/DOM-Level-2-Events/events.html)

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

`explicitOriginalTarget`

No

No

Yes

No

No

No

No

No

Yes

No

No

No

## See also

- [Comparison of Event Targets](comparison_of_event_targets)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/explicitOriginalTarget" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/explicitOriginalTarget</a>
