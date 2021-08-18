# BudgetService.reserve()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `reserve()` property of the [`BudgetService`](../budgetservice) interface returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a boolean indicating whether the requested budget operation can be reserved.

## Syntax

    var aPromise = BudgetService.reserve(operation);
    aPromise.then(function(boolean){ ... });

### Parameters

operation  
desc

### Returns

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves to a boolean.

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

`reserve`

60-70

No

No

No

47-57

No

No

60-70

?

44-49

?

8.0-10.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/BudgetService/reserve" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/BudgetService/reserve</a>
