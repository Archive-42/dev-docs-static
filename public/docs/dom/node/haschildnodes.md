Node.hasChildNodes()
====================

The `Node.hasChildNodes()` method returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) value indicating whether the given [`Node`](../node) has [child nodes](childnodes) or not.

Syntax
------

    bool = node.hasChildNodes();

### Return value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that is `true` if the node has child nodes, and `false` otherwise.

Example
-------

    let foo = document.getElementById('foo');

    if (foo.hasChildNodes()) {
      // Do something with 'foo.childNodes'
    }

Polyfill
--------

Here is one possible polyfill:

    ;(function(prototype) {
      prototype.hasChildNodes = prototype.hasChildNodes || function() {
        return !!this.firstChild;
      }
    })(Node.prototype);

There are various ways to determine whether the node has a child node:

-   `node.hasChildNodes()`
-   `node.firstChild != null` (or just `node.firstChild`)
-   `node.childNodes && node.childNodes.length` (or `node.childNodes.length > 0`)

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-haschildnodes">DOM<br />
<span class="small">The definition of 'Node: hasChildNodes' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [`Node.childNodes`](childnodes)
-   <span class="page-not-created">`Node.hasAttributes`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/hasChildNodes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/hasChildNodes</a>
