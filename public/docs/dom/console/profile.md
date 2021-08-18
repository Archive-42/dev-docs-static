# Console.profile()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Starts recording a performance profile (for example, the [Firefox performance tool](https://developer.mozilla.org/en-US/docs/Tools/Performance)).

You can optionally supply an argument to name the profile and this then enables you to stop only that profile if multiple profiles being recorded. See [`Console.profileEnd()`](profileend) to see how this argument is interpreted.

To stop recording call [`Console.profileEnd()`](profileend).

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

    console.profile(profileName);

## Parameters

`profileName`  
The name to give the profile. Optional.

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

`profile`

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

- [`Console.profileEnd()`](profileend)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Console/profile" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Console/profile</a>
