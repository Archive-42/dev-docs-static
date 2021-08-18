# ChildNode.before()

The `ChildNode.before()` method inserts a set of [`Node`](../node) or [`DOMString`](../domstring) objects in the children list of this `ChildNode`'s parent, just before this `ChildNode`. [`DOMString`](../domstring) objects are inserted as equivalent [`Text`](../text) nodes.

## Syntax

    [Throws, Unscopable]
    void ChildNode.before((Node or DOMString)... nodes);

### Parameters

`nodes`  
A set of [`Node`](../node) or [`DOMString`](../domstring) objects to insert.

### Exceptions

- <span class="page-not-created">`HierarchyRequestError`</span>: Node cannot be inserted at the specified point in the hierarchy.

## Examples

### Inserting an element

    var parent = document.createElement("div");
    var child = document.createElement("p");
    parent.appendChild(child);
    var span = document.createElement("span");

    child.before(span);

    console.log(parent.outerHTML);
    // "<div><span></span><p></p></div>"

### Inserting text

    var parent = document.createElement("div");
    var child = document.createElement("p");
    parent.appendChild(child);

    child.before("Text");

    console.log(parent.outerHTML);
    // "<div>Text<p></p></div>"

### Inserting an element and text

    var parent = document.createElement("div");
    var child = document.createElement("p");
    parent.appendChild(child);
    var span = document.createElement("span");

    child.before(span, "Text");

    console.log(parent.outerHTML);
    // "<div><span></span>Text<p></p></div>"

### `ChildNode.before()` is unscopable

The `before()` method is not scoped into the `with` statement. See [`Symbol.unscopables`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/unscopables) for more information.

    with(node) {
      before("foo");
    }
    // ReferenceError: before is not defined

## Polyfill

You can polyfill the `before()` method in Internet Explorer 9 and higher with the following code:

    // from: https://github.com/jserz/js_piece/blob/master/DOM/ChildNode/before()/before().md
    (function (arr) {
      arr.forEach(function (item) {
        if (item.hasOwnProperty('before')) {
          return;
        }
        Object.defineProperty(item, 'before', {
          configurable: true,
          enumerable: true,
          writable: true,
          value: function before() {
            var argArr = Array.prototype.slice.call(arguments),
              docFrag = document.createDocumentFragment();

            argArr.forEach(function (argItem) {
              var isNode = argItem instanceof Node;
              docFrag.appendChild(isNode ? argItem : document.createTextNode(String(argItem)));
            });

            this.parentNode.insertBefore(docFrag, this);
          }
        });
      });
    })([Element.prototype, CharacterData.prototype, DocumentType.prototype]);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-childnode-before">DOM<br />
<span class="small">The definition of 'ChildNode.before()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`before`

54

17

49

No

39

10

54

54

49

41

10

6.0

## See also

- [`ChildNode.after()`](after)
- [`Element.append()`](../element/append)
- [`Node.appendChild()`](../node/appendchild)
- [`Node.insertBefore()`](../node/insertbefore)
- [`Element.insertAdjacentElement()`](../element/insertadjacentelement)
- [`NodeList`](../nodelist)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/before" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/before</a>
