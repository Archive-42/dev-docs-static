Function.arguments
==================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `function.arguments` property refers to an array-like object corresponding to the arguments passed to a function. Use the simple variable [`arguments`](../../functions/arguments) instead. This property is restricted to non-strict functions.

Description
-----------

The syntax `function.arguments` is deprecated. The recommended way to access the [`arguments`](../../functions/arguments) object available within functions is to refer to the variable [`arguments`](../../functions/arguments).

In the case of recursion, i.e. if function `f` appears several times on the call stack, the value of `f.arguments` represents the arguments corresponding to the most recent invocation of the function.

The value of the arguments property is normally null if there is no outstanding invocation of the function in progress (that is, the function has been called but has not yet returned.

Examples
--------

### Using the arguments object

    function f(n) { g(n - 1) }

    function g(n) {
      console.log('before: ' + g.arguments[0])
      if (n > 0) { f(n) }
      console.log('after: ' + g.arguments[0])
    }

    f(2)

    console.log('returned: ' + g.arguments)

    // Output

    // before: 1
    // before: 0
    // after: 0
    // after: 1
    // returned: null

Specifications
--------------

<span class="pl-s">Not part of any standard.</span> Deprecated in favor of [`arguments`](../../functions/arguments) in ECMAScript 3.

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

`arguments`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

See also
--------

-   [`arguments`](../../functions/arguments) object
-   [Functions and function scope](../../functions)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/arguments" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/arguments</a>
