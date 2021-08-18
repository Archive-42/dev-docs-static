Node
====

The [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) `Node` interface is an abstract base class upon which many other DOM API objects are based, thus letting those object types to be used similarly and often interchangeably. As an abstract class, there is no such thing as a plain `Node` object. All objects that implement `Node` functionality are based on one of its subclasses. Most notable are [`Document`](document), [`Element`](element), and [`DocumentFragment`](documentfragment).

In addition, every kind of DOM node is represented by an interface based on `Node`. These include [`Attr`](attr), [`CharacterData`](characterdata) (which [`Text`](text), [`Comment`](comment), [`CDATASection`](cdatasection) and [`ProcessingInstruction`](processinginstruction) are all based on), [`DocumentType`](documenttype), [`Notation`](notation), <span class="page-not-created">`Entity`</span>, and <span class="page-not-created">`EntityReference`</span>.

In some cases, a particular feature of the base `Node` interface may not apply to one of its child interfaces; in that case, the inheriting node may return `null` or throw an exception, depending on circumstances. For example, attempting to add children to a node type that cannot have children will throw an exception.

Properties
----------

*In addition to the properties below, `Node` inherits properties from its parent, [`EventTarget`](eventtarget)*.

 [`Node.baseURI`](node/baseuri)<span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) representing the base URL of the document containing the `Node`.

 [`Node.childNodes`](node/childnodes)<span class="badge inline readonly">Read only </span>   
Returns a live [`NodeList`](nodelist) containing all the children of this node (including elements, text and comments). [`NodeList`](nodelist) being live means that if the children of the `Node` change, the [`NodeList`](nodelist) object is automatically updated.

 [`Node.firstChild`](node/firstchild)<span class="badge inline readonly">Read only </span>   
Returns a [`Node`](node) representing the first direct child node of the node, or `null` if the node has no child.

 [`Node.isConnected`](node/isconnected)<span class="badge inline readonly">Read only </span>   
A boolean indicating whether or not the Node is connected (directly or indirectly) to the context object, e.g. the [`Document`](document) object in the case of the normal DOM, or the [`ShadowRoot`](shadowroot) in the case of a shadow DOM.

 [`Node.lastChild`](node/lastchild)<span class="badge inline readonly">Read only </span>   
Returns a [`Node`](node) representing the last direct child node of the node, or `null` if the node has no child.

 [`Node.nextSibling`](node/nextsibling)<span class="badge inline readonly">Read only </span>   
Returns a [`Node`](node) representing the next node in the tree, or `null` if there isn't such node.

 [`Node.nodeName`](node/nodename)<span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) containing the name of the `Node`. The structure of the name will differ with the node type. E.g. An [`HTMLElement`](htmlelement) will contain the name of the corresponding tag, like `'audio'` for an [`HTMLAudioElement`](htmlaudioelement), a [`Text`](text) node will have the `'#text'` string, or a [`Document`](document) node will have the `'#document'` string.

 [`Node.nodeType`](node/nodetype)<span class="badge inline readonly">Read only </span>   
Returns an `unsigned short` representing the type of the node. Possible values are:

<table><thead><tr class="header"><th>Name</th><th>Value</th></tr></thead><tbody><tr class="odd"><td><code>ELEMENT_NODE</code></td><td><code>1</code></td></tr><tr class="even"><td><code>ATTRIBUTE_NODE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>2</code></td></tr><tr class="odd"><td><code>TEXT_NODE</code></td><td><code>3</code></td></tr><tr class="even"><td><code>CDATA_SECTION_NODE</code></td><td><code>4</code></td></tr><tr class="odd"><td><code>ENTITY_REFERENCE_NODE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>5</code></td></tr><tr class="even"><td><code>ENTITY_NODE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>6</code></td></tr><tr class="odd"><td><code>PROCESSING_INSTRUCTION_NODE</code></td><td><code>7</code></td></tr><tr class="even"><td><code>COMMENT_NODE</code></td><td><code>8</code></td></tr><tr class="odd"><td><code>DOCUMENT_NODE</code></td><td><code>9</code></td></tr><tr class="even"><td><code>DOCUMENT_TYPE_NODE</code></td><td><code>10</code></td></tr><tr class="odd"><td><code>DOCUMENT_FRAGMENT_NODE</code></td><td><code>11</code></td></tr><tr class="even"><td><code>NOTATION_NODE</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td><code>12</code></td></tr></tbody></table>

[`Node.nodeValue`](node/nodevalue)  
Returns / Sets the value of the current node.

 [`Node.ownerDocument`](node/ownerdocument)<span class="badge inline readonly">Read only </span>   
Returns the [`Document`](document) that this node belongs to. If the node is itself a document, returns `null`.

 [`Node.parentNode`](node/parentnode)<span class="badge inline readonly">Read only </span>   
Returns a [`Node`](node) that is the parent of this node. If there is no such node, like if this node is the top of the tree or if doesn't participate in a tree, this property returns `null`.

 [`Node.parentElement`](node/parentelement)<span class="badge inline readonly">Read only </span>   
Returns an [`Element`](element) that is the parent of this node. If the node has no parent, or if that parent is not an [`Element`](element), this property returns `null`.

 [`Node.previousSibling`](node/previoussibling)<span class="badge inline readonly">Read only </span>   
Returns a [`Node`](node) representing the previous node in the tree, or `null` if there isn't such node.

[`Node.textContent`](node/textcontent)  
Returns / Sets the textual content of an element and all its descendants.

Methods
-------

*In addition to the properties below, `Node` inherits methods from its parent, [`EventTarget`](eventtarget).*

[`Node.appendChild(childNode)`](node/appendchild)  
Adds the specified `childNode` argument as the last child to the current node.  
If the argument referenced an existing node on the DOM tree, the node will be detached from its current position and attached at the new position.

[`Node.cloneNode()`](node/clonenode)  
Clone a [`Node`](node), and optionally, all of its contents. By default, it clones the content of the node.

[`Node.compareDocumentPosition()`](node/comparedocumentposition)  
Compares the position of the current node against another node in any other document.

[`Node.contains()`](node/contains)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether or not a node is a descendant of the calling node.

 <span class="page-not-created">`Node.getBoxQuads()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a list of the node's CSS boxes relative to another node.

[`Node.getRootNode()`](node/getrootnode)  
Returns the context object's root which optionally includes the shadow root if it is available.

[`Node.hasChildNodes()`](node/haschildnodes)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or not the element has any child nodes.

[`Node.insertBefore()`](node/insertbefore)  
Inserts a [`Node`](node) before the reference node as a child of a specified parent node.

[`Node.isDefaultNamespace()`](node/isdefaultnamespace)  
Accepts a namespace URI as an argument and returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) with a value of `true` if the namespace is the default namespace on the given node or `false` if not.

[`Node.isEqualNode()`](node/isequalnode)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) which indicates whether or not two nodes are of the same type and all their defining data points match.

[`Node.isSameNode()`](node/issamenode)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether or not the two nodes are the same (that is, they reference the same object).

[`Node.lookupPrefix()`](node/lookupprefix)  
Returns a [`DOMString`](domstring) containing the prefix for a given namespace URI, if present, and `null` if not. When multiple prefixes are possible, the result is implementation-dependent.

[`Node.lookupNamespaceURI()`](node/lookupnamespaceuri)  
Accepts a prefix and returns the namespace URI associated with it on the given node if found (and `null` if not). Supplying `null` for the prefix will return the default namespace.

[`Node.normalize()`](node/normalize)  
Clean up all the text nodes under this element (merge adjacent, remove empty).

[`Node.removeChild()`](node/removechild)  
Removes a child node from the current element, which must be a child of the current node.

[`Node.replaceChild()`](node/replacechild)  
Replaces one child [`Node`](node) of the current one with the second one given in parameter.

### Obsolete methods

 [`Node.getUserData()`](node/getuserdata) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Allows a user to get some [`DOMUserData`](domuserdata) from the node.

 <span class="page-not-created">`Node.hasAttributes()`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element has any attributes, or not.

 [`Node.isSupported()`](node/issupported) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) flag containing the result of a test whether the DOM implementation implements a specific feature and this feature is supported by the specific node.

 [`Node.setUserData()`](node/setuserdata) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Allows a user to attach, or remove, [`DOMUserData`](domuserdata) to the node.

Examples
--------

### Remove all children nested within a node

    function removeAllChildren(element) {
      while (element.firstChild) {
        element.removeChild(element.firstChild)
      }
    }

#### Sample usage

    /* Note: or use document.body.textContent = "" */
    removeAllChildren(document.body)

### Recurse through child nodes

The following function recursively calls a callback function for each node contained by a root node (including the root itself):

    function eachNode(rootNode, callback) {
        if (!callback) {
            const nodes = []
            eachNode(rootNode, function(node) {
                nodes.push(node)
            })
            return nodes
        }

        if (false === callback(rootNode)) {
            return false
        }

        if (rootNode.hasChildNodes()) {
            const nodes = rootNode.childNodes
            for (let i = 0, l = nodes.length; i < l; ++i) {
                if (false === eachNode(nodes[i], callback)) {
                    return
                }
            }
        }
    }

#### Syntax

    eachNode(rootNode, callback)

#### Description

Recursively calls a function for each descendant node of `rootNode` (including the root itself).

If `callback` is omitted, the function returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) instead, which contains `rootNode` and all nodes contained within.

If `callback` is provided, and it returns [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) `false` when called, the current recursion level is aborted, and the function resumes execution at the last parent's level. This can be used to abort loops once a node has been found (such as searching for a text node which contains a certain string).

#### Parameters

`rootNode`  
The `Node` object whose descendants will be recursed through.

 `callback` <span class="badge inline optional">Optional</span>   
An optional callback [function](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function) that receives a `Node` as its only argument. If omitted, `eachNode` returns an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) of every node contained within `rootNode` (including the root itself).

#### Sample usage

The following example prints the [`textContent`](node/textcontent) properties of each `<span>` tag in a `<div>` element named `"box"`:

    <div id="box">
      <span>Foo</span>
      <span>Bar</span>
      <span>Baz</span>
    </div>

    const box = document.getElementById("box")
    eachNode(box, function(node) {
      if (null != node.textContent) {
        console.log(node.textContent)
      }
    })

The above will result in the following strings printing to the user's console:

    "\n\t", "Foo", "\n\t", "Bar", "\n\t", "Baz"

**Note:** Whitespace forms part of a [`Text`](text) node, meaning indentation and newlines form separate `Text` between the `Element` nodes.

#### Realistic usage

The following demonstrates a real-world use of the `eachNode()` function: searching for text on a web-page.

We use a wrapper function named `grep` to do the searching:

    function grep(parentNode, pattern) {
        const matches = []
        let endScan = false

        eachNode(parentNode, function(node){
            if (endScan) {
                return false
            }

            // Ignore anything which isn't a text node
            if (node.nodeType !== Node.TEXT_NODE) {
                return
            }

            if (typeof pattern === "string") {
                if (-1 !== node.textContent.indexOf(pattern)) {
                    matches.push(node)
                }
            }
            else if (pattern.test(node.textContent)) {
                if (!pattern.global) {
                    endScan = true
                    matches = node
                }
                else {
                    matches.push(node)
                }
            }
        })

        return matches
    }

For example, to find [`Text`](text) nodes that contain typos:

    const typos = ["teh", "adn", "btu", "adress", "youre", "msitakes"]
    const pattern = new RegExp("\\b(" + typos.join("|") + ")\\b", "gi")
    const mistakes = grep(document.body, pattern)
    console.log(mistakes)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-node">DOM<br />
<span class="small">The definition of 'Node' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the following methods: <code>getRootNode()</code></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#interface-node">DOM4<br />
<span class="small">The definition of 'Node' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Removed the following properties: <code>attributes</code>, <code>namespaceURI</code>, <code>prefix</code>, and <code>localName</code>.<br />
Removed the following methods: <code>isSupported()</code>, <code>hasAttributes()</code>, <code>getFeature()</code>, <code>setUserData()</code>, and <code>getUserData()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-1950641247">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Node' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The methods <code>insertBefore()</code>, <code>replaceChild()</code>, <code>removeChild()</code>, and <code>appendChild()</code> returns one more kind of error (<code>NOT_SUPPORTED_ERR</code>) if called on a <a href="document"><code>Document</code></a>.<br />
The <code>normalize()</code> method has been modified so that <a href="text"><code>Text</code></a> node can also be normalized if the proper <span class="page-not-created"><code>DOMConfiguration</code></span> flag is set.<br />
Added the following methods: <code>compareDocumentPosition()</code>, <code>isSameNode()</code>, <code>lookupPrefix()</code>, <code>isDefaultNamespace()</code>, <code>lookupNamespaceURI()</code>, <code>isEqualNode()</code>, <code>getFeature()</code>, <code>setUserData()</code>, and <code>getUserData().</code><br />
Added the following properties: <code>baseURI</code> and <code>textContent</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-1950641247">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Node' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>ownerDocument</code> property was slightly modified so that <a href="documentfragment"><code>DocumentFragment</code></a> also returns <code>null</code>.<br />
Added the following properties: <code>namespaceURI</code>, <code>prefix</code>, and <code>localName</code>.<br />
Added the following methods: <code>normalize()</code>, <code>isSupported()</code> and <code>hasAttributes()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-1950641247">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Node' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Node`

1

WebKit and old versions of Blink incorrectly do not make `Node` inherit from `EventTarget`.

12

1

5

7

WebKit and old versions of Blink incorrectly do not make `Node` inherit from `EventTarget`.

1

WebKit and old versions of Blink incorrectly do not make `Node` inherit from `EventTarget`.

1

WebKit and old versions of Blink incorrectly do not make `Node` inherit from `EventTarget`.

18

WebKit and old versions of Blink incorrectly do not make `Node` inherit from `EventTarget`.

4

10.1

WebKit and old versions of Blink incorrectly do not make `Node` inherit from `EventTarget`.

1

WebKit and old versions of Blink incorrectly do not make `Node` inherit from `EventTarget`.

1.0

WebKit and old versions of Blink incorrectly do not make `Node` inherit from `EventTarget`.

`appendChild`

1

12

1

5

7

1.1

1

18

4

10.1

1

1.0

`baseURI`

1

12

1

No

≤12.1

7

1

18

4

≤12.1

7

1.0

`childNodes`

1

12

1

5

7

1.2

1

18

4

10.1

1

1.0

`cloneNode`

1

12

1

6

7

1.1

1

18

4

10.1

1

1.0

`compareDocumentPosition`

1

12

9

9

Only supports `contains` for elements

≤12.1

4

1

18

9

≤12.1

3.2

1.0

`contains`

16

12

9

9

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Node` objects.

7

1.1

≤37

18

9

10.1

1

1.0

`firstChild`

1

12

1

6

≤12.1

7

1

18

4

≤12.1

7

1.0

`getFeature`

No

No

No

No

≤12.1-15

No

No

No

No

≤12.1-14

No

No

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

`getUserData`

No

No

1-22

No

No

No

No

No

4-22

No

No

No

`hasAttributes`

1-27

12-79

No

9

≤12.1-15

1-6.1

No

No

No

≤12.1-14

1-7

No

`hasChildNodes`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

`insertBefore`

1

12

3

6

7

1.1

1

18

4

10.1

1

1.0

`isConnected`

51

79

53

No

38

10

51

51

45

41

10

6.0

`isDefaultNamespace`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`isEqualNode`

1

12

2

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`isSameNode`

1

12

48

1-10

9

≤12.1

3

1

18

48

4-10

≤12.1

1

1.0

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

`lastChild`

1

12

1

6

≤12.1

7

1

18

45

≤12.1

7

1.0

`lookupNamespaceURI`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`lookupPrefix`

1

12

1

9

≤12.1

3

1

18

4

≤12.1

1

1.0

`nextSibling`

1

12

1

5.5

7

1.1

1

18

4

10.1

1

1.0

`nodeName`

1

12

1

6

≤12.1

7

1

18

4

≤12.1

7

1.0

`nodeType`

1

12

1

6

7

1.1

1

18

4

10.1

1

1.0

`nodeValue`

1

12

1

6

≤12.1

7

1

18

4

≤12.1

7

1.0

`normalize`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`ownerDocument`

1

12

9

1-9

The `ownerDocument` of doctype nodes (that is, nodes for which `Node.nodeType` is `Node.DOCUMENT_TYPE_NODE` or 10) is `null`.

6

≤12.1

7

1

18

9

4-9

The `ownerDocument` of doctype nodes (that is, nodes for which `Node.nodeType` is `Node.DOCUMENT_TYPE_NODE` or 10) is `null`.

≤12.1

7

1.0

`parentElement`

1

12

9

9

Only supported on `Element`.

7

Before Opera 15, this feature was only supported on `Element`.

1.1

1

18

9

10.1

Before Opera Android 14, this feature was only supported on `Element`.

1

1.0

`parentNode`

1

12

1

5.5

7

1.1

1

18

4

10.1

1

1.0

`previousSibling`

1

12

1

5.5

≤12.1

7

1

18

4

≤12.1

7

1.0

`removeChild`

1

12

1

5

7

1.1

1

18

4

10.1

1

1.0

`replaceChild`

1

12

1

6

7

1.1

1

18

4

10.1

1

1.0

`setUserData`

No

No

1-22

No

No

No

No

No

4-22

No

No

No

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node</a>
