MutationObserverInit.attributes
===============================

The **[`MutationObserverInit`](../mutationobserverinit)** dictionary's optional `attributes` property is used to specify whether or not to watch for attribute value changes on the node or nodes being observed.

Syntax
------

    var options = {
      attributes: true | false
    }

### Value

A Boolean value indicating whether or not to report through the callback any changes to the values of attributes on the node or nodes being monitored. The default value is `false`.

If `true`, the callback specified when [`observe()`](../mutationobserver/observe) was used to start observing the node or subtree will be called any time one or more attributes have changed on observed nodes.

You can expand the capabilities of attribute mutation monitoring using other options:

-   [`attributeFilter`](attributefilter) lets you specify specific attribute names to monitor instead of monitoring all attributes.
-   [`attributeOldValue`](attributeoldvalue) lets you specify whether or not you want the previous value of changed attributes to be included in the [`MutationRecord`](../mutationrecord)'s <span class="page-not-created">`oldValue`</span> property.
-   [`subtree`](subtree) lets you specify whether to watch the target node and all of its descendants (`true`), or just the target node (`false`).

If you set either `attributeFilter` or `attributeOldValue` to `true`, `attributes` is automatically assumed to be `true`, even if you don't expressly set it as such.

Example
-------

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

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-mutationobserverinit-attributes">DOM<br />
<span class="small">The definition of 'MutationObserverInit.attributes' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`attributes`

18

12

14

Starting in Firefox 36, `attributes` has no default value; previously, its default value was `false`.

11

15

6

≤37

18

14

Starting in Firefox 36, `attributes` has no default value; previously, its default value was `false`.

14

6

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/attributes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/attributes</a>
