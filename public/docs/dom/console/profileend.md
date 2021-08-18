# Console.profileEnd()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Calling this API immediately after console.profile() can cause it to not work. To work around this, call it in a setTimeout with at least 5ms delay. See [bug 1240249](https://bugzilla.mozilla.org/show_bug.cgi?id=1240249).

The profileEnd method stops recording a profile previously started with [`Console.profile()`](profile).

You can optionally supply an argument to name the profile. Doing so enables you to stop only that profile if you have multiple profiles being recorded.

- if `Console.profileEnd()` is passed a profile name, and it matches the name of a profile being recorded, then that profile is stopped.
- if `Console.profileEnd()` is passed a profile name and it does not match the name of a profile being recorded, no changes will be made.
- if `Console.profileEnd()` is not passed a profile name, the most recently started profile is stopped.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    console.profileEnd(profileName);

## Parameters

`profileName`  
The name to give the profile. This parameter is optional.

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

`profileEnd`

4

12

16

9

11

4

≤37

18

16

11

3.2

1.0

## See also

- [`Console.profile()`](profile)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console/profileEnd" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console/profileEnd</a>
