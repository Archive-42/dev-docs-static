WorkerGlobalScope.close()
=========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `close()` method of the [`WorkerGlobalScope`](../workerglobalscope) interface discards any tasks queued in the `WorkerGlobalScope`'s event loop, effectively closing this particular scope.

Syntax
------

    self.close();

Example
-------

If you wanted to close your worker instance from inside the worker itself, you could call the following:

    close();

`close()` and `self.close()` are effectively equivalent — both represent `close()` being called from inside the worker's inner scope.

**Note**: there is also a way to stop the worker from the main thread: the [`Worker.terminate`](../worker/terminate) method.

Browser compatibility
---------------------

No compatibility data found for `api.WorkerGlobalScope.close`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

[`WorkerGlobalScope`](../workerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/close" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/close</a>
