# Node.getRootNode()

The `getRootNode()` method of the [`Node`](../node) interface returns the context object's root, which optionally includes the shadow root if it is available.

## Syntax

    var root = node.getRootNode(options);

### Parameters

`options` <span class="badge inline optional">Optional</span>  
An object that sets options for getting the root node. The available options are:

- `composed`: A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether the shadow root should be returned (`false`, the default), or a root node beyond shadow root (`true`).

### Returns

An object inheriting from [`Node`](../node). This will differ in exact form depending on where you called `getRootNode()`; for example:

- Calling it on an element inside a standard web page will return an [`HTMLDocument`](../htmldocument) object representing the entire page.
- Calling it on an element inside a shadow DOM will return the associated [`ShadowRoot`](../shadowroot).

## Examples

The first simple example returns a reference to the HTML/document node:

    rootNode = node.getRootNode();

This more complex example shows the difference between returning a normal root, and a root including the shadow root. (See the [full source code](<https://github.com/jserz/js_piece/blob/master/DOM/Node/getRootNode()/demo/getRootNode.html>)):

    <!-- source: https://github.com/jserz/js_piece/blob/master/DOM/Node/getRootNode()/demo/getRootNode.html -->
    <div class="js-parent">
      <div class="js-child"></div>
    </div>
    <div class="js-shadowHost"></div>
    <script>
      // works on Chrome 54+, Opera 41+

      var parent = document.querySelector('.js-parent'),
          child = document.querySelector('.js-child'),
          shadowHost = document.querySelector('.js-shadowHost');

      console.log(parent.getRootNode().nodeName); // #document
      console.log(child.getRootNode().nodeName); // #document

      // create a ShadowRoot
      var shadowRoot = shadowHost.attachShadow({mode:'open'});
      shadowRoot.innerHTML = '<style>div{background:#2bb8aa;}</style>'
          + '<div class="js-shadowChild">content</div>';
      var shadowChild = shadowRoot.querySelector('.js-shadowChild');

      // The default value of composed is false
      console.log(shadowChild.getRootNode() === shadowRoot); // true
      console.log(shadowChild.getRootNode({composed:false}) === shadowRoot); // true
      console.log(shadowChild.getRootNode({composed:true}).nodeName); // #document
    </script>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-getrootnode">DOM<br />
<span class="small">The definition of 'getRootNode()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`getRootNode`

54

79

53

No

41

10.1

54

54

53

41

10.3

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/getRootNode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/getRootNode</a>
