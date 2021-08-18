# Node.textContent

The `textContent` property of the [`Node`](../node) interface represents the text content of the node and its descendants.

**Note:** `textContent` and [`HTMLElement.innerText`](../htmlelement/innertext) are easily confused, but the two properties are [different in important ways](#differences_from_innertext).

## Syntax

    let text = someNode.textContent
    someOtherNode.textContent = string

### Value

A string or [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null)

## Description

The value of `textContent` depends on the situation:

- If the node is a [`document`](../document) or a [Doctype](https://developer.mozilla.org/en-US/docs/Glossary/Doctype), `textContent` returns [`null`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null).
  **Note:** To get _all_ of the text and [CDATA data](../cdatasection) for the whole document, one could use `document.documentElement.textContent`.

- If the node is a [CDATA section](../cdatasection), comment, [processing instruction](../processinginstruction), or [text node](../text), `textContent` returns the text inside the node, i.e., the [`Node.nodeValue`](nodevalue).
- For other node types, `textContent` returns the concatenation of the `textContent` of every child node, excluding comments and processing instructions. (This is an empty string if the node has no children.)

Setting `textContent` on a node removes _all_ of the node's children and replaces them with a single text node with the given string value.

### Differences from innerText

Don't get confused by the differences between `Node.textContent` and [`HTMLElement.innerText`](../htmlelement/innertext). Although the names seem similar, there are important differences:

- `textContent` gets the content of _all_ elements, including [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) and [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) elements. In contrast, `innerText` only shows “human-readable” elements.
- `textContent` returns every element in the node. In contrast, `innerText` is aware of styling and won’t return the text of “hidden” elements.
  - Moreover, since `innerText` takes CSS styles into account, reading the value of `innerText` triggers a [reflow](https://developer.mozilla.org/en-US/docs/Glossary/Reflow) to ensure up-to-date computed styles. (Reflows can be computationally expensive, and thus should be avoided when possible.)
- Unlike `textContent`, altering `innerText` in Internet Explorer (version 11 and below) removes child nodes from the element and _permanently destroys_ all descendant text nodes. It is impossible to insert the nodes again into any other element or into the same element after doing so.

### Differences from innerHTML

[`Element.innerHTML`](../element/innerhtml) returns HTML, as its name indicates. Sometimes people use `innerHTML` to retrieve or write text inside an element, but `textContent` has better performance because its value is not parsed as HTML.

Moreover, using `textContent` can prevent [XSS attacks](https://developer.mozilla.org/en-US/docs/Glossary/Cross-site_scripting).

## Examples

Given this HTML fragment:

    <div id="divA">This is <span>some</span> text!</div>

... you can use `textContent` to get the element's text content:

    let text = document.getElementById('divA').textContent;
    // The text variable is now: 'This is some text!'

... or set the element's text content:

    document.getElementById('divA').textContent = 'This text is different!';
    // The HTML for divA is now:
    // <div id="divA">This text is different!</div>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-textcontent">DOM<br />
<span class="small">The definition of 'Node.textContent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`textContent`

1

12

1

9

9

3

1

18

4

10.1

1

1.0

## See also

- [`HTMLElement.innerText`](../htmlelement/innertext)
- [`Element.innerHTML`](../element/innerhtml)
- [More on differences between `innerText` and `textContent`](http://perfectionkills.com/the-poor-misunderstood-innerText/) (blog post)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/textContent</a>
