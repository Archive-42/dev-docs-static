HTMLImageElement.name
=====================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`HTMLImageElement`](../htmlimageelement) interface's *deprecated* `name` property specifies a name for the element. This has been replaced by the [`id`](../element/id) property available on all elements.

Syntax
------

    htmlImageElement.name = nameString;
    nameString = htmlImageElement.name;

### Value

A [`DOMString`](../domstring) providing a name by which the image can be referenced.

**Important:** This property is deprecated and is only in the specification still for backward compatibility purposes. Since it functions identically to [`id`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-id), you can and should use it instead.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#attr-img-name">HTML Living Standard<br />
<span class="small">The definition of 'HTMLImageElement.name' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/struct/objects.html#adef-name-IMG">HTML 4.01 Specification<br />
<span class="small">The definition of 'HTMLImageElement.name' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Provides additional details not available in the HTML 5</td></tr></tbody></table>

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

`name`

1

12

1

5.5

≤12.1

3

1

Yes

4

≤12.1

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/name" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/name</a>
