Web Locks API
=============

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The Web Locks API allows scripts running in one tab or worker to asynchronously acquire a lock, hold it while work is performed, then release it. While held, no other script executing in the same origin can acquire the same lock, which allows a web app running in multiple tabs or workers to coordinate work and the use of resources.

Web Locks Concepts and Usage
----------------------------

A lock is an abstract concept representing some potentially shared resource, identified by a name chosen by the web app. For example, if a web app running in multiple tabs wants to ensure that only one tab is syncing data between the network and Indexed DB, each tab could try to acquire a "my\_net\_db\_sync" lock, but only one tab will succeed (the [leader election pattern](https://en.wikipedia.org/wiki/Leader_election).)

The API is used as follows:

1.  The lock is requested.
2.  Work is done while holding the lock in an asynchronous task.
3.  The lock is automatically released when the task completes.

<!-- -->

    navigator.locks.request('my_resource', async lock => {
      // The lock has been acquired.
      await do_something();
      await do_something_else();
      // Now the lock will be released.
    });

While a lock is held, requests for the same lock from this execution context, or from other tabs/workers, will be queued. The first queued request will be granted only when the lock is released.

The API provides optional functionality that may be used as needed, including:

-   returning values from the asynchronous task
-   shared and exclusive lock modes
-   conditional acquisition
-   diagnostics to query the state of locks in an origin
-   an escape hatch to protect against deadlocks

Locks are scoped to origins; the locks acquired by a tab from https://example.com have no effect on the locks acquired by a tab from https://example.org:8080 as they are separate origins.

The main entry point is `navigator.locks.request()` which requests a lock. It takes a lock name, an optional set of options, and a callback. The callback is invoked when the lock is granted. The lock is automatically released when the callback returns, so usually the callback is an *async function*, which causes the lock to be released only when the async function has completely finished.

The `request()` method itself returns a promise which resolves once the lock has been released; within an async function, a script can `await` the call to make the asynchronous code flow linear. For example:

    await do_something_without_lock();

    // Request the lock.
    await navigator.locks.request('my_resource', async lock => {
      // The lock has been acquired.
      await do_something_with_lock();
      await do_something_else_with_lock();
      // Now the lock will be released.
    });
    // The lock has been released.

    await do_something_else_without_lock();

### Options

Several options can be passed when requesting a lock:

-   `mode`: The default mode is "exclusive", but "shared" can be specified. There can be only one "exclusive" holder of a lock, but multiple "shared" requests can be granted at the same time. This can be used to implement the [readers-writer pattern](https://en.wikipedia.org/wiki/Readers%E2%80%93writer_lock).
-   `signal`: An **AbortSignal** can be passed in, allowing a lock request to be aborted. This can be used to implement a timeout on requests.
-   `ifAvailable`: If specified, the lock request will fail if the lock cannot be granted immediately without waiting. The callback is invoked with `null`.

### Monitoring

The `navigator.locks.query()` method can be used by scripts to introspect the state of the lock manager for the origin. This can be useful when debugging, for example, identifying why a lock could not be acquired. The results are a snapshot of the lock manager state, which identifies held and requested locks and some additional data (e.g. mode) about each, at the time the snapshot was taken.

### Advanced use

For more complicated cases, such as holding the lock for an arbitrary amount of time, the callback can return a promise explicitly resolved by the script:

    // Capture promise control functions:
    let resolve, reject;
    const p = new Promise((res, rej) => { resolve = res; reject = rej; });

    // Request the lock:
    navigator.locks.request('my_resource', lock => {
      // Lock is acquired.

      return p;
      // Now lock will be held until either resolve() or reject() is called.
    });

### Deadlocks

A deadlock occurs when a process can no longer make progress because each part is waiting on a request that cannot be satisfied. This can occur with this API in complex use-cases, for example, if multiple locks are requested out-of-order. If tab 1 holds lock A and tab 2 holds lock B, then tab 1 attempts to also acquire lock B and tab 2 attempts to also acquire lock A, neither request can be granted. Web applications can avoid this through several strategies, such as ensuring lock requests are not nested, or are always well ordered, or have timeouts. Note that such deadlocks only affect the locks themselves and code depending on them; the browser, other tabs, and other script in the page is not affected.

Interfaces
----------

[`Lock`](lock)  
Provides the name and mode of a previously requested lock, which is received in the callback to [`LockManager.request()`](lockmanager/request).

[`LockManager`](lockmanager)  
Provides methods for requesting a new [`Lock`](lock) object and querying for an existing Lock object. To get an instance of LockManager, call [`navigator.locks`](navigator/locks).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/web-locks/">Web Locks API</a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Web_Locks_API`

69

≤79

?

No

56

No

69

69

?

48

No

10.0

`mode`

69

≤79

?

No

56

No

69

69

?

48

No

10.0

`name`

69

≤79

?

No

56

No

69

69

?

48

No

10.0

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

`Web_Locks_API`

69

≤79

?

No

56

No

69

69

?

48

No

10.0

`query`

69

≤79

?

No

56

No

69

69

?

48

No

10.0

`request`

69

≤79

?

No

56

No

69

69

?

48

No

10.0

BCD tables only load in the browser

### Lock

BCD tables only load in the browser

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Web_Locks_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Web_Locks_API</a>
