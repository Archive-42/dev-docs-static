# Node.isConnected

The `isConnected` read-only property of the [`Node`](../node) interface returns a boolean indicating whether the node is connected (directly or indirectly) to the context object, for example the [`Document`](../document) object in the case of the normal DOM, or the [`ShadowRoot`](../shadowroot) in the case of a shadow DOM.

## Syntax

    var isItConnected = nodeObjectInstance.isConnected

### Return value

`true` if the node is connected to its relevant context object, and `false` if not.

## Examples

### Standard DOM

A standard DOM example:

    let test = document.createElement('p');
    console.log(test.isConnected); // Returns false
    document.body.appendChild(test);
    console.log(test.isConnected); // Returns true

### Shadow DOM

A shadow DOM example:

    // Create a shadow root
    var shadow = this.attachShadow({mode: 'open'});

    // Create some CSS to apply to the shadow dom
    var style = document.createElement('style');
    console.log(style.isConnected); // returns false

    style.textContent = `
    .wrapper {
      position: relative;
    }

    .info {
      font-size: 0.8rem;
      width: 200px;
      display: inline-block;
      border: 1px solid black;
      padding: 10px;
      background: white;
      border-radius: 10px;
      opacity: 0;
      transition: 0.6s all;
      positions: absolute;
      bottom: 20px;
      left: 10px;
      z-index: 3
    }
    `;

    // Attach the created style element to the shadow dom

    shadow.appendChild(style);
    console.log(style.isConnected); // Returns true

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-node-isconnected">DOM<br />
<span class="small">The definition of 'isConnected' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

## See also

- [Node.prototype.isConnected polyfill](https://gist.github.com/eligrey/f109a6d0bf4efe3461201c3d7b745e8f)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Node/isConnected" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Node/isConnected</a>
