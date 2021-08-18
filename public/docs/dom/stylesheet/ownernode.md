StyleSheet.ownerNode
====================

The `ownerNode` property of the [`StyleSheet`](../stylesheet) interface returns the node that associates this style sheet with the document.

This is usually an HTML `<link>` or `<style>` element, but can also return a [processing instruction node](../processinginstruction) in the case of `<?xml-stylesheet ?>`.

Syntax
------

    nodeRef = stylesheet.ownerNode

Example
-------

    <html lang="en">
     <head>
      <link rel="stylesheet" href="example.css">
     </head>
     <body>
       <button onclick="alert(document.styleSheets[0].ownerNode)">Show example.css’s ownerNode</button>
     </body>
    </html>
    // Displays "object HTMLLinkElement"

Notes
-----

For style sheets that are included by other style sheets, such as with `@import`, the value of this property is `null`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-stylesheet-ownernode">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'StyleSheet: ownerNode' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`ownerNode`

1

12

1

9

Yes

1

Yes

Yes

4

Yes

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet/ownerNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet/ownerNode</a>
