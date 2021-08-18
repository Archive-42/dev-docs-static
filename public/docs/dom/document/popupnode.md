# Document.popupNode

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note:** Starting with Gecko 2.0, authors are encouraged to use the [menupopup](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL/menupopup) property [triggerNode](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL/Property/triggerNode) instead.

When a popup attached via the `popup` or `context` attributes is opened, the XUL document's `popupNode` property is set to the node that was clicked on. This will be the target of the mouse event that activated the popup. If the popup was opened via the keyboard, the popup node may be set to null. Typically, this property will be checked during a popupshowing event handler for a context menu to initialize the menu based on the context.

This property is only set for popups attached via the `popup` or `context` attributes. For other types of popups, the value is not changed. In these other cases, for example when calling the popup's [showPopup](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL/Method/showPopup) method, you may wish to set the `popupNode` property directly beforehand.

This property applies only to XUL documents.

## Syntax

    var node = document.popupNode;

## Example

    <menupopup id="toolbarContextMenu">
      ...
      <menuitem oncommand="mailNewsCore.deleteButton(document.popupNode)">
      ...
    </menupopup>

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

`popupNode`

No

No

Yes

Available only to [XUL documents](https://developer.mozilla.org/docs/Mozilla/Tech/XUL).

No

No

No

No

No

No

No

No

No

## See also

- Defined in [nsIDOMXULDocument.idl](https://dxr.mozilla.org/mozilla-central/source/dom/public/idl/xul/nsIDOMXULDocument.idl#48). XUL-specific method. Not part of any specification.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/popupNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/popupNode</a>
