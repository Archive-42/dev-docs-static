Node.removeChild()
==================

The `Node.removeChild()` method removes a child node from the DOM and returns the removed node.

Syntax
------

    var oldChild = node.removeChild(child);

Or just:

    node.removeChild(child);

-   `child` is the child node to be removed from the DOM.
-   `node` is the parent node of `child`.
-   `oldChild` holds a reference to the removed child node, i.e., `oldChild === child`.

The removed child node still exists in memory, but is no longer part of the DOM. With the first syntax form shown, you may reuse the removed node later in your code, via the `oldChild` object reference.

In the second syntax form, however, there is no `oldChild` reference kept, so assuming your code has not kept any other reference to the node elsewhere, it will immediately become unusable and irretrievable, and will usually be [automatically deleted](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management) from memory after a short time.

If `child` is actually not a child of the `element` node, the method throws an exception. This will also happen if `child` was in fact a child of `element` at the time of the call, but was removed by an event handler invoked in the course of trying to remove the element (e.g., `blur`.)

### Errors thrown

The method throws an exception in 2 different ways:

1.  If the `child` was in fact a child of `element` and so existing on the DOM, but was removed the method throws the following exception:

    `Uncaught NotFoundError: Failed to execute 'removeChild' on 'Node': The node to be removed is not a child of this node`.

2.  If the `child` doesn't exist on the DOM of the page, the method throws the following exception:  
      
    `Uncaught TypeError: Failed to execute 'removeChild' on 'Node': parameter 1 is not of type 'Node'.`

Examples
--------

### Simple examples

Given this HTML:

    <div id="top">
      <div id="nested"></div>
    </div>

To remove a specified element when knowing its parent node:

    let d = document.getElementById("top");
    let d_nested = document.getElementById("nested");
    let throwawayNode = d.removeChild(d_nested);

To remove a specified element without having to specify its parent node:

    let node = document.getElementById("nested");
    if (node.parentNode) {
      node.parentNode.removeChild(node);
    }

To remove all children from an element:

    let element = document.getElementById("top");
    while (element.firstChild) {
      element.removeChild(element.firstChild);
    }

### Causing a TypeError

    <!--Sample HTML code-->
    <div id="top"> </div>

    <script type="text/javascript">
      let top = document.getElementById("top");
      let nested = document.getElementById("nested");

      // Throws Uncaught TypeError
      let garbage = top.removeChild(nested);
    </script>

### Causing a NotFoundError

    <!--Sample HTML code-->
    <div id="top">
      <div id="nested"></div>
    </div>

    <script type="text/javascript">
      let top = document.getElementById("top");
      let nested = document.getElementById("nested");

      // This first call correctly removes the node
      let garbage = top.removeChild(nested);

      // Throws Uncaught NotFoundError
      garbage = top.removeChild(nested);
    </script>

Notes
-----

Unlike [`Node.cloneNode()`](clonenode) the return value preserves the [`EventListener`](../eventlistener)s.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-removechild">DOM<br />
<span class="small">The definition of 'Node: removeChild' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

See also
--------

-   [`Node.replaceChild()`](replacechild)
-   [`Node.parentNode`](parentnode)
-   [`ChildNode.remove()`](../childnode/remove)
-   [`Node.cloneNode()`](clonenode)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild</a>
