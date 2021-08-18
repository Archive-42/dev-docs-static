# MutationObserverInit.subtree

The **[`MutationObserverInit`](../mutationobserverinit)** dictionary's optional `subtree` property can be set to `true` to monitor the targeted node _and_ all of its descendants. The default value, `false`, indicates only the target node itself is to be monitored for changes.

`subtree` can be used in concert with the other options to extend monitoring of attributes, text content, and child lists to the entire subtree rooted at the target node.

## Syntax

    var options = {
      subtree: true | false
    }

### Value

A Boolean value. The default, `false`, indicates that only the target node specified when calling [`MutationObserver.observe()`](../mutationobserver/observe) is to be monitored for changes. Changing this value to `true` causes the entire subtree rooted at the specified target node to be monitored for the changes indicated by the other options.

For example, to watch the target node only for attribute changes, the [`MutationObserverInit`](../mutationobserverinit) passed into [`MutationObserver()`](../mutationobserver/mutationobserver) can be:

    var options = {
      attributes: true,
      subtree: false
    };

Since the default value of `subtree` is `false`, line 3 is optional.

To monitor the entire subtree for attribute changes, set `subtree` to `true`:

    var options = {
      attributes: true,
      subtree: true
    };

## Example

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-mutationobserverinit-subtree">DOM<br />
<span class="small">The definition of 'MutationObserverInit.subtree' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/subtree" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/subtree</a>
