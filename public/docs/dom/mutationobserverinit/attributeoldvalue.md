# MutationObserverInit.attributeOldValue

The **[`MutationObserverInit`](../mutationobserverinit)** dictionary's optional `attributeOldValue` property is used to specify whether or not to record the prior value of the altered attribute in [`MutationRecord`](../mutationrecord) objects denoting attribute value changes.

## Syntax

    var options = {
      attributeOldValue: true | false
    }

### Value

A Boolean value indicating whether or not the prior value of a changed attribute should be included in the <span class="page-not-created">`MutationObserver.oldValue`</span> property when reporting attribute value changes. If `true`, `oldValue` is set accordingly. If `false`, it is not.

When using `attributeOldValue`, setting the [`attributes`](attributes) option to `true` is optional.

## Example

In this example, a Mutation Observer is set up to watch for changes to the `status` and `username` attributes in any elements contained within a subtree that displays the names of users in a chat room. This lets the code, for example, reflect changes to users' nicknames, or to mark them as away from keyboard (AFK) or offline.

    function callback(mutationList) {
      mutationList.forEach(function(mutation) {
        switch(mutation.type) {
          case "attributes":
            notifyUser("Attribute name " + mutation.attributeName +
                " changed to " + mutation.target[mutation.attributeName] +
                " (was " + mutation.oldValue + ")");
            break;
        }
      });
    }

    var targetNode = document.querySelector("#target");

    var observer = new MutationObserver(callback);
    observer.observe(targetNode, {
      attributes: true,
      attributeOldValue: true
    });

The `callback()` function—which will be passed into the [`observe()`](../mutationobserver/observe) method when starting the observer, looks at each item in the list of [`MutationRecord`](../mutationrecord) objects. For any items representing an attribute change (which can be detected by the value of <span class="page-not-created">`MutationRecord.type`</span> being `"attributes"`), a function called `notifyUser()` is used to tell the user the name of the attribute that changed as well as the attribute's new value (`mutation.target[mutation.attributeName]`) and its old value (`mutation.oldValue`).

When `observe()` is called, the specified options are `attributes` and `attributeOldValue`, which means that changes to attribute values will be reported, and each mutation record will include the <span class="page-not-created">`oldValue`</span> property specifying the attribute's previous value.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-mutationobserverinit-attributeoldvalue">DOM<br />
<span class="small">The definition of 'MutationObserverInit.attributeOldValue' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`attributeOldValue`

18

12

14

Starting in Firefox 36, `attributeOldValue` has no default value; previously, its default value was `false`.

11

15

6

≤37

18

14

Starting in Firefox 36, `attributeOldValue` has no default value; previously, its default value was `false`.

14

6

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/attributeOldValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/attributeOldValue</a>
