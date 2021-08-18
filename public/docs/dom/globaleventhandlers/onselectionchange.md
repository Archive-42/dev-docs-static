GlobalEventHandlers.onselectionchange
=====================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onselectionchange` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `selectionchange` events.

The `selectionchange` event fires when the text selected on a webpage changes.

Syntax
------

    object.onselectionchange = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`FocusEvent`](../focusevent) object as its sole argument.

Example
-------

    let selection;

    document.onselectionchange = function() {
      console.log('New selection made');
      selection = document.getSelection();
    };

For a full example, see our [Key quote generator](https://github.com/chrisdavidmills/selection-api-examples/#key-quote-generator-see-it-running-live) demo.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-globaleventhandlers-onselectionchange">Selection API<br />
<span class="small">The definition of 'GlobalEventHandlers.onselectionchange' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onselectionchange`

11

12

52

5.5

15

5.1

≤37

18

52

14

5

1.0

See also
--------

-   `selectionchange` event
-   Related event handler: [`GlobalEventHandlers.onselectstart`](onselectstart)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectionchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectionchange</a>
