# ChildNode.remove()

The `ChildNode.remove()` method removes the object from the tree it belongs to.

## Syntax

    node.remove();

## Example

### Using `remove()`

    <div id="div-01">Here is div-01</div>
    <div id="div-02">Here is div-02</div>
    <div id="div-03">Here is div-03</div>

    var el = document.getElementById('div-02');
    el.remove(); // Removes the div with the 'div-02' id

### `ChildNode.remove()` is unscopable

The `remove()` method is not scoped into the `with` statement. See [`Symbol.unscopables`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Symbol/unscopables) for more information.

    with(node) {
      remove();
    }
    // ReferenceError: remove is not defined

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-childnode-remove">DOM<br />
<span class="small">The definition of 'ChildNode.remove' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`remove`

23

12

23

No

15

7

≤37

25

23

14

7

1.5

## See also

- The [`ChildNode`](../childnode) pure interface.
- Object types implementing this pure interface: [`CharacterData`](../characterdata), [`Element`](../element), and [`DocumentType`](../documenttype).

- [Polyfill](https://github.com/chenzhenxi/element-remove)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/remove" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ChildNode/remove</a>
