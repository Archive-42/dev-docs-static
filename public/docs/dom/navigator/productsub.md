# Navigator.productSub

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Navigator.productSub` read-only property returns the build number of the current browser.

## Syntax

    prodSub = window.navigator.productSub

- `prodSub` is a string.

## Example

    <script>
    function prodsub() {
      var dt = document.getElementById("d").childNodes[0];
      dt.data = window.navigator.productSub;
    }
    </script>

    <button onclick="prodsub();">productSub</button>
    // returns: 20010725

## Notes

On IE, this property returns undefined.

On Apple Safari and Google Chrome this property always returns `20030107`.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-navigator-productsub">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorID: productSub' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`productSub`

1

Always returns `20030107`.

12

Always returns `20030107`.

1

No

15

Always returns `20030107`.

1

Always returns `20030107`.

1

Always returns `20030107`.

18

Always returns `20030107`.

4

14

Always returns `20030107`.

1

Always returns `20030107`.

1.0

Always returns `20030107`.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/productSub" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/productSub</a>
