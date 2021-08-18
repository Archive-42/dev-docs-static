LockManager.request()
=====================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `request()` method of the [`LockManager`](../lockmanager) interface requests a [`Lock`](../lock) object with parameters specifying its name and characteristics. The requested `Lock` is passed to a callback, while the function itself returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with [`undefined`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/undefined).

The `mode` property of the `options` parameter may be either `"exclusive"` or `"shared"`.

Request an `"exclusive"` lock when it should only be held by one code instance at a time. This applies to code in both tabs and workers. Use this to represent mutually exclusive access to a resource. When an `"exclusive"` lock for a given name is held, no other lock with the same name can be held.

Request a `"shared"` lock when multiple instances of the code can share access to a resource. When a `"shared"` lock for a given name is held, other `"shared"` locks for the same name can be granted, but no `"exclusive"` locks with that name can be held or granted.

This shared/exclusive lock pattern is common in database transaction architecture, for example to allow multiple simultaneous readers (each requests a `"shared"` lock) but only one writer (a single `"exclusive"` lock). This is known as the readers-writer pattern. In the [IndexedDB API](../indexeddb_api), this is exposed as `"readonly"` and `"readwrite"` transactions which have the same semantics.

Syntax
------

    LockManager.request(var promise = name[, {options}], callback)

### Parameters

name  
An identifier for the lock you want to request.

options <span class="badge inline optional">Optional</span>   
An object describing characteristics of the lock you want to create. Valid values are:

-   `mode` <span class="badge inline optional">Optional</span>: Either `"exclusive"` or `"shared"`. The default value is `"exclusive"`.
-   `ifAvailable` <span class="badge inline optional">Optional</span>: If `true`, the lock request will only be granted if it is not already held. If it cannot be granted, the callback will be invoked with `null` instead of a `Lock` instance. The default value is `false`.
-   `steal` <span class="badge inline optional">Optional</span>: If `true`, then any held locks with the same name will be released, and the request will be granted, preempting any queued requests for it. The default value is `false`.
-   `signal` <span class="badge inline optional">Optional</span>: An `AbortSignal` (the `signal` property of an `AbortController`); if specified and the `AbortController` is aborted, the lock request is dropped if it was not already granted.

callback  
…

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that resolves with undefined when the request is granted.

Examples
--------

### General Example

The following example shows the basic use of the `request()` method with an asynchronous function as the callback. Once the callback is invoked, no other running code on this origin can hold \``my_resource`\` until the callback returns.

    await navigator.locks.request('my_resource', async lock => {
      // The lock was granted.
    });

### Mode Example

The following example shows how to use the `mode` option for readers and writers.

Notice that both functions use a lock called `my_resource`. The `do_read()` requests a lock in `'shared'` mode meaning that multiple calls may occur simultaneously across different event handlers, tabs, or workers.

    async function do_read() {
      await navigator.locks.request('my_resource', {mode: 'shared'}, async lock => {
        // Read code here.
      });
    }

The `do_write()` function use the same lock but in `'exclusive'` mode which will delay invocation of the `request()` call in `do_read()` until the write operation has completed. This applies across event handlers, tabs, or workers.

    function do_write() {
      await navigator.locks.request('my_resource', {mode: 'exclusive'}, async lock => {
        // Write code here.
      });
    }

### ifAvailable Example

To grab a lock only if it isn't already being held, use the `ifAvailable` option. In this function `await` means the method will not return until the callback is complete. Since the lock is only granted if it was available, this call avoids needing to wait on the lock being released elsewhere.

    await navigator.locks.request('my_resource', {ifAvailable: true}, async lock => {
      if (!lock) {
        // The lock was not granted - get out fast.
        return;
      }

      // The lock was granted, and no other running code in this origin is holding
      // the 'my_res_lock' lock until this returns.
    });

### signal Example

To only wait for a lock for a short period of time, use the `signal` option.

    const controller = new AbortController();
    // Wait at most 200ms.
    setTimeout(() => controller.abort(), 200);

    try {
      await navigator.locks.request('my_resource', {signal: controller.signal}, async lock => {
        // The lock was acquired!
      });
    } catch (ex) {
      if (ex.name === 'AbortError') {
        // The request aborted before it could be granted.
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/web-locks/#dom-lockmanager-request">Web Locks API<br />
<span class="small">The definition of 'request()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/LockManager/request" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/LockManager/request</a>
