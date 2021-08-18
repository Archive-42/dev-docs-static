# DOMImplementation.hasFeature()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `DOMImplementation.hasFeature()` method returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag indicating if a given feature is supported. It is deprecated and modern browsers return `true` in all cases.

The different implementations fairly diverged in what kind of features were reported. The latest version of the spec settled to force this method to always return `true`, where the functionality was accurate and in use.

## Syntax

    const flag = document.implementation.hasFeature(feature, version);

### Parameters

`feature`  
A [`DOMString`](../domstring) representing the feature name.

`version`  
A [`DOMString`](../domstring) representing the version of the specification defining the feature.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-domimplementation-hasfeature">DOM<br />
<span class="small">The definition of 'DOMImplementation.hasFeature' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Modified to always return <code>true</code> except for SVG features.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-5CED94D7">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'DOMImplementation.hasFeature' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-5CED94D7">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'DOMImplementation.hasFeature' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-5CED94D7">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'DOMImplementation.hasFeature' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`hasFeature`

1

12

1

Since Firefox 19, `hasFeature()` mostly returns `true`.

6

≤12.1

1

1

18

4

≤12.1

1

1.0

## See also

- The [`DOMImplementation`](../domimplementation) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation/hasFeature" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/DOMImplementation/hasFeature</a>
