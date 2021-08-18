Text.replaceWholeText()
=======================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Text.replaceWholeText()` method replaces the text of the node and all of its logically adjacent text nodes with the specified text. The replaced nodes are removed, including the current node, unless it was the recipient of the replacement text.

A [`DOMException`](../domexception) with the value `NO_MODIFICATION_ERR` is thrown if one of the text nodes being replaced is read only.

This method returns the text node which received the replacement text, or `null` if the replacement text is an empty string. The returned node is the current node unless the current node is read only, in which case the returned node is a newly created text node of the same type which has been inserted at the location of the replacement.

Syntax
------

    replacementNode = textnode.replaceWholeText(content) 

Example
-------

See the example for the [`Text.wholeText`](wholetext) property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-1312295772">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Text' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`replaceWholeText`

Yes-45

12-79

Yes-10

9

Yes-32

4-10.1

Yes-45

Yes-45

Yes-10

Yes-32

3-10.3

Yes-5.0

See also
--------

-   The [`Text`](../text) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Text/replaceWholeText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Text/replaceWholeText</a>
