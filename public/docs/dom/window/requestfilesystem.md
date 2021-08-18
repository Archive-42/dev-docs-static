Window.requestFileSystem()
==========================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The non-standard [`Window`](../window) method `requestFileSystem()` method is a Google Chrome-specific method which lets a web site or app gain access to a sandboxed file system for its own use. The returned [`FileSystem`](../filesystem) is then available for use with the other [file system APIs](../file_and_directory_entries_api).

Even compared to the rest of the File and Directory Entries API, `requestFileSystem()` is especially non-standard; only Chrome implements it, and all other browser makers have decided that they will not implement it. It has even been removed from [the proposed specification](https://wicg.github.io/entries-api/). *Do not use this method!*

Syntax
------

This method is prefixed with `webkit` in all browsers that implement it (that is, Google Chrome).

    window.requestFileSystem(type, size, successCallback[, errorCallback]);

### Parameters

`type`  
The type of storage to request. Specify `Window.TEMPORARY` if it's acceptable for the browser to delete the files at its own discretion, such as if storage space runs low, or `Window.PERSISTENT` if you need the files to remain in place unless the user or the web site or app explicitly permit it. Persistent storage requires that the user grant the site quota.

`size`  
The amount of storage space you wish to have allocated for your app's use.

`successCallback`  
A function which is invoked when the file system has been successfully obtained. The callback receives a single parameter: a [`FileSystem`](../filesystem) object representing the file system the app has permission to use.

 `errorCallback` <span class="badge inline optional">Optional</span>   
An optional parameter specifying a function which is called if an error occurs while attempting to obtain the file system, or if the user denies permission to create or access the file system. The callback receives as input a single parameter: a [`FileError`](../fileerror) object describing the error.

### Return value

`undefined`

Example
-------

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://wicg.github.io/entries-api/">File and Directory Entries API</a></td><td><span class="spec-draft">Draft</span></td><td>Draft of proposed API</td></tr></tbody></table>

This API has no official W3C or WHATWG specification.

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

`requestFileSystem`

13

≤18

No

No

No

No

37

Yes

No

No

No

Yes

See also
--------

-   [File and Directory Entries API support in Firefox](../file_and_directory_entries_api/firefox_support)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/requestFileSystem" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/requestFileSystem</a>
