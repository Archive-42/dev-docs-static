# Node.isSupported()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Node.isSupported()`returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag containing the result of a test whether the DOM implementation implements a specific feature and this feature is supported by the specific node.

## Syntax

    boolValue = element.isSupported(feature, version)

### Parameters

_feature_  
Is a [`DOMString`](../domstring) containing the name of the feature to test. This is the same name which can be passed to the method `hasFeature` on [DOMImplementation](../document/implementation). Possible values defined within the core DOM specification are listed on the DOM Level 2 [Conformance Section](https://www.w3.org/TR/DOM-Level-2-Core/introduction.html#ID-Conformance).

_version_  
Is a [`DOMString`](../domstring) containing the version number of the feature to test. In DOM Level 2, version 1, this is the string `2.0`. If the version is not specified, supporting any version of the feature will cause the method to return true.

## Example

    <div id="doc">
    </div>

    <script>
     // Get an element and check to see if its supports the DOM2 HTML Module.
     var main = document.getElementById('doc');
     var output = main.isSupported('HTML', '2.0');
    </script>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#Level-2-Core-Node-supports">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node.isSupported()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Core/">Document Object Model (DOM) Level 2 Core Specification</a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#Level-2-Core-Node-supports">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node.isSupported()' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`isSupported`

1-34

No

1-22

9

≤12.1-21

1-10

1-37

18-34

4-22

≤12.1-21

1-10

1.0-2.0

## See also

- The [`Node`](../node) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/isSupported" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/isSupported</a>
