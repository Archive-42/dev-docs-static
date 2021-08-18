NavigatorPlugins.mimeTypes
==========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Returns a [`MimeTypeArray`](../mimetypearray) object, which contains a list of [`MimeType`](../mimetype) objects representing the MIME types recognized by the browser.

**Note**: Named properties of [`MimeTypeArray`](../mimetypearray) objects are no longer enumerable in the latest browser versions.

Syntax
------

    var mimeTypes[] = navigator.mimeTypes;

`mimeTypes` is a `MimeTypeArray` object which has a `length` property as well as `item(index)` and `namedItem(name)` methods.

Example
-------

    function isJavaPresent() {
      return 'application/x-java-applet' in navigator.mimeTypes;
    }

    function getJavaPluginDescription() {
      var mimetype = navigator.mimeTypes['application/x-java-applet'];
      if (mimetype === undefined) {
        // no Java plugin present
        return undefined;
      }
      return mimetype.enabledPlugin.description;
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-navigator-mimetypes">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorPlugins.mimeTypes' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`mimeTypes`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorPlugins/mimeTypes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorPlugins/mimeTypes</a>
