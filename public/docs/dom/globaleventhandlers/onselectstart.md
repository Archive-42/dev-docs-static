GlobalEventHandlers.onselectstart
=================================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `onselectstart` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `selectstart` events.

The `selectstart` event fires when the user starts to make a new text selection on a webpage.

Syntax
------

    object.onselectstart = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function). The function receives a [`FocusEvent`](../focusevent) object as its sole argument.

Examples
--------

    document.onselectstart = function() {
      console.log('Selection started!');
    };

For a full example, see our [Key quote generator](https://github.com/chrisdavidmills/selection-api-examples/#key-quote-generator-see-it-running-live) demo.

    document.onselectstart = () => {
      return false; // cancel selection
    };

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/selection-api/#dom-globaleventhandlers-onselectstart">Selection API<br />
<span class="small">The definition of 'GlobalEventHandlers.onselectstart' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`onselectstart`

1

12

52

4

15

1.3

1

18

52

14

1

The `selectstart` event never fires and never invokes this handler.

1.0

See also
--------

-   `selectstart` event
-   Related event handler: [`GlobalEventHandlers.onselectionchange`](onselectionchange)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectstart" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onselectstart</a>
