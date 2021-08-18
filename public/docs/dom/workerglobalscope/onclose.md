WorkerGlobalScope.onclose
=========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

Summary
-------

The `onclose` property of the [`WorkerGlobalScope`](../workerglobalscope) interface represents an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) to be called when the `close` event occurs and bubbles through the [`Worker`](../worker).

This non-standard event handler was only implemented by a few browsers and has been removed from all or nearly all of them.

Syntax
------

    self.onclose = function() { ... };

Example
-------

The following code snippet shows an `onclose` handler set inside a worker:

    self.onclose = function() {
      console.log('Your worker instance has been closed');
    }

Specifications
--------------

This feature is no longer defined in any specifications.

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

`onclose`

4

12

3.5-50

Yes

11.5

4

37

40

4-50

Yes

5.1

4.0

See also
--------

-   The [`WorkerGlobalScope`](../workerglobalscope) interface it belongs to.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onclose" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/onclose</a>
