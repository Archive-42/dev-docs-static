WorkerGlobalScope.dump()
========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `dump()` method of the [`WorkerGlobalScope`](../workerglobalscope) interface allows you to write a message to stdout — i.e. in your terminal, in Firefox only. This is the same as Firefox's [`window.dump`](../window/dump), but for workers.

Syntax
------

    dump('My message\n');

### Parameters

A [`DOMString`](../domstring) containing the message you want to send.

### Returns

Void.

Example
-------

To write an output from your worker to your computer's terminal, you first have to run an instance of Firefox started from your command line/terminal. For example, on Mac OS X you'd run it using something like this (assuming you are inside the `Applications` folder):

    ./Firefox.app/Contents/MacOS/firefox-bin -profile /tmp -no-remote

Now go into `about:config` and enable the `browser.dom.window.dump.enabled` pref.

Next, run a worker containing the following line:

    dump('test\n');

This should result in a "test" message being output to the terminal.

Specifications
--------------

This method does not appear in any specification.

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

`dump`

No

No

No

No

No

No

No

No

4

No

No

No

See also
--------

[`WorkerGlobalScope`](../workerglobalscope)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/dump" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WorkerGlobalScope/dump</a>
