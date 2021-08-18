# MutationObserver.MutationObserver()

The DOM `MutationObserver()` constructor — part of the [`MutationObserver`](../mutationobserver) interface — creates and returns a new observer which invokes a specified callback when DOM events occur. DOM observation does not begin immediately; the [`observe()`](observe) method must be called first to establish which portion of the DOM to watch and what kinds of changes to watch for.

## Syntax

    const observer = new MutationObserver(callback)

### Parameters

`callback`  
A function which will be called on each DOM change that qualifies given the observed node or subtree and options.

The `callback` function takes as input two parameters:

1.  An array of [`MutationRecord`](../mutationrecord) objects, describing each change that occurred; and
2.  the [`MutationObserver`](../mutationobserver) which invoked the `callback`.

See the [example](#example) below for more details.

### Return value

A new [`MutationObserver`](../mutationobserver) object, configured to call the specified `callback` when DOM mutations occur.

## Example

This example creates a new `MutationObserver` configured to watch a node and all of its children for additions and removals of elements to the tree, as well as any changes to attributes on any of the elements in the tree.

### The callback function

    function callback(mutationList, observer) {
      mutationList.forEach( (mutation) => {
        switch(mutation.type) {
          case 'childList':
            /* One or more children have been added to and/or removed
               from the tree.
               (See mutation.addedNodes and mutation.removedNodes.) */
            break;
          case 'attributes':
            /* An attribute value changed on the element in
               mutation.target.
               The attribute name is in mutation.attributeName, and
               its previous value is in mutation.oldValue. */
            break;
        }
      });
    }

The `callback()` function is invoked when the observer sees changes matching the configuration of the observation request specified when calling [`observe()`](observe) to begin watching the DOM.

The kind of change that took place (either a change to the list of children, or a change to an attribute) is detected by looking at the <span class="page-not-created">`mutation.type`</span> property.

### Creating and starting the observer

This code actually sets up the observation process.

    const targetNode = document.querySelector("#someElement");
    const observerOptions = {
      childList: true,
      attributes: true,

      // Omit (or set to false) to observe only changes to the parent node
      subtree: true
    }

    const observer = new MutationObserver(callback);
    observer.observe(targetNode, observerOptions);

The desired subtree is located by finding an element with the ID `someElement`. A set of options for the observer is also established in the `observerOptions` record. In it, we specify values of `true` for both `childList` and `attributes`, so we get the information we want.

Then the observer is instantiated, specifying the `callback()` function. We begin observing the DOM nodes of interest by calling `observe()`, specifying the `target` node and the `options` object.

From this point until [`disconnect()`](disconnect) is called, `callback()` will be called each time an element is added to or removed from the DOM tree rooted at `targetNode`, or any of those elements' attributes are changed.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-mutationobserver-mutationobserver">DOM<br />
<span class="small">The definition of 'MutationObserver()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`MutationObserver`

26

18

12

14

11

15

7

6

≤37

≤37

26

18

14

14

7

6

1.5

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/MutationObserver" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserver/MutationObserver</a>
