MutationObserverInit
====================

The `MutationObserverInit` dictionary describes the configuration of a mutation observer. As such, it's primarily used as the type of the `options` parameter on the [`MutationObserver.observe()`](mutationobserver/observe) method.

Properties
----------

At a minimum, one of `childList`, `attributes`, and/or `characterData` must be `true` when you call [`observe()`](mutationobserver/observe). Otherwise, a `TypeError` exception will be thrown.

 [`subtree`](mutationobserverinit/subtree) <span class="badge inline optional">Optional</span>   
Set to `true` to extend monitoring to the entire subtree of nodes rooted at `target`. All of the other `MutationObserverInit` properties are then extended to all of the nodes in the subtree instead of applying solely to the `target` node. The default value is `false`.

 [`childList`](mutationobserverinit/childlist) <span class="badge inline optional">Optional</span>   
Set to `true` to monitor the target node (and, if `subtree` is `true`, its descendants) for the addition of new child nodes or removal of existing child nodes. The default value is `false`.

 [`attributes`](mutationobserverinit/attributes) <span class="badge inline optional">Optional</span>   
Set to `true` to watch for changes to the value of attributes on the node or nodes being monitored. The default value is `true` if either of `attributeFilter` or `attributeOldValue` is specified, otherwise the default value is `false`.

 [`attributeFilter`](mutationobserverinit/attributefilter) <span class="badge inline optional">Optional</span>   
An array of specific attribute names to be monitored. If this property isn't included, changes to all attributes cause mutation notifications.

 [`attributeOldValue`](mutationobserverinit/attributeoldvalue) <span class="badge inline optional">Optional</span>   
Set to `true` to record the previous value of any attribute that changes when monitoring the node or nodes for attribute changes; see [Monitoring attribute values](mutationobserver#monitoring_attribute_values) in [MutationObserver](mutationobserver) for details on watching for attribute changes and value recording. The default value is `false`.

 [`characterData`](mutationobserverinit/characterdata) <span class="badge inline optional">Optional</span>   
Set to `true` to monitor the specified target node (and, if `subtree` is `true`, its descendants) for changes to the character data contained within the node or nodes. The default value is `true` if `characterDataOldValue` is specified, otherwise the default value is `false`.

 [`characterDataOldValue`](mutationobserverinit/characterdataoldvalue) <span class="badge inline optional">Optional</span>   
Set to `true` to record the previous value of a node's text whenever the text changes on nodes being monitored. For details and an example, see [Monitoring text content changes](mutationobserver#monitoring_text_content_changes) in [MutationObserver](mutationobserver). The default value is `false`.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dictdef-mutationobserverinit">DOM<br />
<span class="small">The definition of 'MutationObserverInit' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`MutationObserverInit`

26

18-26

12

14

11

15

7

6-7

≤37

26

18-26

14

14

7

6-7

1.5

1.0-1.5

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

`characterData`

18

12

14

Starting in Firefox 36, `characterData` has no default value; previously, its default value was `false`.

11

15

6

≤37

18

14

Starting in Firefox 36, `characterData` has no default value; previously, its default value was `false`.

14

6

1.0

`characterDataOldValue`

18

12

14

Starting in Firefox 36, `characterDataOldValue` has no default value; previously, its default value was `false`.

11

15

6

≤37

18

14

Starting in Firefox 36, `characterDataOldValue` has no default value; previously, its default value was `false`.

14

6

1.0

`childList`

18

12

14

11

15

6

≤37

18

14

14

6

1.0

`subtree`

18

12

14

11

15

6

≤37

18

14

14

6

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit</a>
