# MutationObserverInit.attributeFilter

The **[`MutationObserverInit`](../mutationobserverinit)** dictionary's optional `attributeFilter` property is an array of strings specifying the names of the attributes whose values are to be monitored for changes. If this property is specified, there's no need to also set [`attributes`](attributes) to `true`, as it's implied.

If the [`attributes`](attributes) permission is `true` but no `attributeFilter` is included in the options object, all attributes' values are watched for changes.

## Syntax

    var options = {
      attributeFilter: [ "list", "of", "attribute", "names" ]
    }

### Value

An array of [`DOMString`](../domstring) objects, each specifying the name of one attribute whose value is to be monitored for changes. There is no default value.

If this property exists on the options object when the [`MutationObserver()`](../mutationobserver/mutationobserver) constructor is used to create a new `MutationObserver`, attribute monitoring is enabled regardless of whether or not the [`attributes`](attributes) property is `true`.

## Example

In this example, a Mutation Observer is set up to watch for changes to the `status` and `username` attributes in any elements contained within a subtree that displays the names of users in a chat room. This lets the code, for example, reflect changes to users' nicknames, or to mark them as away from keyboard (AFK) or offline.

    function callback(mutationList) {
      mutationList.forEach(function(mutation) {
        switch(mutation.type) {
          case "attributes":
            switch(mutation.attributeName) {
              case "status":
                userStatusChanged(mutation.target.username, mutation.target.status);
                break;
              case "username":
                usernameChanged(mutation.oldValue, mutation.target.username);
                break;
            }
            break;
        }
      });
    }

    var userListElement = document.querySelector("#userlist");

    var observer = new MutationObserver(callback);
    observer.observe(userListElement, {
      attributeFilter: [ "status", "username" ],
      attributeOldValue: true,
      subtree: true
    });

The `callback()` function—which will be passed into the [`observe()`](../mutationobserver/observe) method when starting the observer, looks at each item in the list of [`MutationRecord`](../mutationrecord) objects. For any items representing an attribute change (which can be detected by the value of <span class="page-not-created">`MutationRecord.type`</span> being `"attributes"`), we use the attribute's name, obtained using <span class="page-not-created">`MutationRecord.attributeName`</span>, to identify the type of change that occurred and then dispatch to the appropriate handler function.

Note the use of <span class="page-not-created">`MutationRecord.oldValue`</span> to get the previous value of the `"username"` property so we have that information when doing lookups in our local array of users.

When `observe()` is called, the specified options include both `attributeFilter` and [`subtree`](subtree), so that we monitor the attribute values for all of the nodes contained within the subtree rooted at the node with the ID `"userlist"`. The [`attributeOldValue`](attributeoldvalue) option is set to `true` because we want the prior value of the changed attributes recorded and reported in the mutation records we receive.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-mutationobserverinit-attributefilter">DOM<br />
<span class="small">The definition of 'MutationObserverInit: attributeFilter' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`attributeFilter`

18

12

Before Edge 79, this requires `attributes: true` when using `attributeFilter`. If `attributes: true` is not present, then Edge throws a syntax error.

14

11

Internet Explorer requires `attributes: true` when using `attributeFilter`. If `attributes: true` is not present, then Internet Explorer throws a syntax error.

15

6

≤37

18

14

14

6

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/attributeFilter" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/attributeFilter</a>
