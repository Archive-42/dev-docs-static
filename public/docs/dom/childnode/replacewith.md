# ChildNode.replaceWith()

The `ChildNode.replaceWith()` method replaces this `ChildNode` in the children list of its parent with a set of [`Node`](../node) or [`DOMString`](../domstring) objects. [`DOMString`](../domstring) objects are inserted as equivalent [`Text`](../text) nodes.

## Syntax

    [Throws, Unscopable]
    void ChildNode.replaceWith((Node or DOMString)... nodes);

### Parameters

`nodes`  
A set of [`Node`](../node) or [`DOMString`](../domstring) objects to replace.

### Exceptions

- <span class="page-not-created">`HierarchyRequestError`</span>: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Using `replaceWith()`

    var parent = document.createElement("div");
    var child = document.createElement("p");
    parent.appendChild(child);
    var span = document.createElement("span");

    child.replaceWith(span);

    console.log(parent.outerHTML);
    // "<div><span></span></div>"

### `ChildNode.replaceWith()` is unscopable

The `replaceWith()` method is not scoped into the `with` statement. See [`Symbol.unscopables`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/unscopables) for more information.

    with(node) {
      replaceWith("foo");
    }
    // ReferenceError: replaceWith is not defined

## Polyfill

You can polyfill the `replaceWith()` method in Internet Explorer 10+ and higher with the following code:

    function ReplaceWithPolyfill() {
      'use-strict'; // For safari, and IE > 10
      var parent = this.parentNode, i = arguments.length, currentNode;
      if (!parent) return;
      if (!i) // if there are no arguments
        parent.removeChild(this);
      while (i--) { // i-- decrements i and returns the value of i before the decrement
        currentNode = arguments[i];
        if (typeof currentNode !== 'object'){
          currentNode = this.ownerDocument.createTextNode(currentNode);
        } else if (currentNode.parentNode){
          currentNode.parentNode.removeChild(currentNode);
        }
        // the value of "i" below is after the decrement
        if (!i) // if currentNode is the first argument (currentNode === arguments[0])
          parent.replaceChild(currentNode, this);
        else // if currentNode isn't the first
          parent.insertBefore(currentNode, this.nextSibling);
      }
    }
    if (!Element.prototype.replaceWith)
        Element.prototype.replaceWith = ReplaceWithPolyfill;
    if (!CharacterData.prototype.replaceWith)
        CharacterData.prototype.replaceWith = ReplaceWithPolyfill;
    if (!DocumentType.prototype.replaceWith)
        DocumentType.prototype.replaceWith = ReplaceWithPolyfill;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-childnode-replacewith">DOM<br />
<span class="small">The definition of 'ChildNode.replacewith()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`replaceWith`

54

17

49

No

39

Yes

54

54

49

41

Yes

6.0

## See also

- [`ChildNode`](../childnode) and [`ParentNode`](../parentnode)
- [`Node.replaceChild()`](../node/replacechild)
- [`NodeList`](../nodelist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/replaceWith" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/replaceWith</a>
