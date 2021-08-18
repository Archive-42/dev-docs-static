# Document.anchors

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `anchors` read-only property of the [`Document`](../document) interface returns a list of all of the anchors in the document.

## Syntax

    nodeList = document.anchors;

### Value

An [`HTMLCollection`](../htmlcollection).

## Example

    if (document.anchors.length >= 5) {
      dump("found too many anchors");
    }

The following is an example that auto populates a Table of Contents with every anchor on the page:

    <!DOCTYPE html>
    <html lang="en">
    <head>
    <meta charset="UTF-8" />
    <title>Test</title>
    <script>
    function init() {
      var toc = document.getElementById("toc");
      var i, li, newAnchor;
      for (i = 0; i < document.anchors.length; i++) {
        li = document.createElement("li");
        newAnchor = document.createElement('a');
        newAnchor.href = "#" + document.anchors[i].name;
        newAnchor.textContent = document.anchors[i].text;
        li.appendChild(newAnchor);
        toc.appendChild(li);
      }
    }
    </script>
    </head>
    <body onload="init()">

    <h1>Title</h1>
    <h2><a name="contents">Contents</a></h2>
    <ul id="toc"></ul>

    <h2><a name="plants">Plants</a></h2>
    <ol>
      <li>Apples</li>
      <li>Oranges</li>
      <li>Pears</li>
    </ol>

    <h2><a name="veggies">Veggies</a></h2>
    <ol>
      <li>Carrots</li>
      <li>Celery</li>
      <li>Beats</li>
    </ol>

    </body>
    </html>

[View on JSFiddle](https://jsfiddle.net/S4yNp)

## Notes

For reasons of backwards compatibility, the returned set of anchors only contains those anchors created with the `name` attribute, not those created with the `id` attribute.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-document-anchors">HTML Living Standard<br />
<span class="small">The definition of 'Document.anchors' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Obsoleted.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-7577272">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'Document.anchors' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`anchors`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/anchors" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/anchors</a>
