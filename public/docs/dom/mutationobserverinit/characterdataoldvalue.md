# MutationObserverInit.characterDataOldValue

The **[`MutationObserverInit`](../mutationobserverinit)** dictionary's optional `characterDataOldValue` property is used to specify whether or not the <span class="page-not-created">`MutationRecord.oldValue`</span> property for DOM mutations should be set to the previous value of text nodes which changed.

If you set the [`MutationObserverInit.characterData`](characterdata) property to `true` but don't set `characterDataOldValue` to `true` as well, the `MutationRecord` will not include information describing the prior state of the text node's contents.

Character data changes are detectable on any text node, including nodes based on the [`Text`](../text), [`ProcessingInstruction`](../processinginstruction), and [`Comment`](../comment) interfaces.

## Syntax

    var options = {
      characterDataOldValue: true | false
    }

### Value

A Boolean value indicating whether or not to set the `MutationRecord`'s `oldValue` property to be a string containing the value of the character node's contents prior to the change represented by the mutation record.

By default, only changes to the text of the node specified as the `target` parameter when you called [`observe()`](../mutationobserver/observe) are monitored. To watch for changes to the text contents of all descendants of `target`, set the [`subtree`](subtree) option to `true`.

If you set `characterDataOldValue` to `true`, `characterData` is automatically assumed to be `true`, even if you don't expressly set it as such.

## Example

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-mutationobserverinit-characterdataoldvalue">DOM<br />
<span class="small">The definition of 'MutationObserverInit.characterDataOldValue' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/characterDataOldValue" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationObserverInit/characterDataOldValue</a>
