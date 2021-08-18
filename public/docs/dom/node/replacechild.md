# Node.replaceChild()

The `Node.replaceChild()` method replaces a child node within the given (parent) node.

Note the idiosyncratic argument order (new before old). `ChildNode.replaceWith()` may be easier to read and use.

## Syntax

    let oldChild = parentNode.replaceChild(newChild, oldChild);

### Parameters

**newChild**  
The new node to replace `oldChild`. If it already exists in the DOM, it is first removed.

**oldChild**  
The child to be replaced.

### Return value

The returned value is the replaced node. This is the same node as `oldChild`.

## Example

    // Given:
    // <div>
    //  <span id="childSpan">foo bar</span>
    // </div>

    // Create an empty element node
    // without an ID, any attributes, or any content
    var sp1 = document.createElement("span");

    // Give it an id attribute called 'newSpan'
    sp1.id = "newSpan";

    // Create some content for the new element.
    var sp1_content = document.createTextNode("new replacement span element.");

    // Apply that content to the new element
    sp1.appendChild(sp1_content);

    // Build a reference to the existing node to be replaced
    var sp2 = document.getElementById("childSpan");
    var parentDiv = sp2.parentNode;

    // Replace existing node sp2 with the new span element sp1
    parentDiv.replaceChild(sp1, sp2);

    // Result:
    // <div>
    //   <span id="newSpan">new replacement span element.</span>
    // </div>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-replacechild">DOM<br />
<span class="small">The definition of 'Node: replaceChild' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

## See also

- [`Node.removeChild`](removechild)
- [`ChildNode.replaceWith`](../childnode/replacewith)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/replaceChild" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/replaceChild</a>
