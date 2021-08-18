Large-Allocation
================

The non-standard `Large-Allocation` response header tells the browser that the page being loaded is going to want to perform a large allocation. It is currently only implemented in Firefox, but is harmless to send to every browser.

[WebAssembly](https://developer.mozilla.org/en-US/docs/WebAssembly) or asm.js applications can use large contiguous blocks of allocated memory. For complex games, for example, these allocations can be quite large, sometimes as large as 1GB. The `Large-Allocation` tells the browser that the web content in the to-be-loaded page is going to want to perform a large contiguous memory allocation and the browser can react to this header by starting a dedicated process for the to-be-loaded document, for example.

<table><tbody><tr class="odd"><td>Header type</td><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Response_header">Response header</a></td></tr><tr class="even"><td><a href="https://developer.mozilla.org/en-US/docs/Glossary/Forbidden_header_name">Forbidden header name</a></td><td>no</td></tr></tbody></table>

Syntax
------

    Large-Allocation: 0
    Large-Allocation: <megabytes>

Directives
----------

`0`  
0 is a special value which represents uncertainty as to what the size of the allocation is.

`<megabytes>`  
The expected size of the allocation to be performed, in megabytes.

Examples
--------

    Large-Allocation: 0
    Large-Allocation: 500

Troubleshooting errors
----------------------

The `Large-Allocation` header throws warnings or error messages when used incorrectly. You'll encounter them in the [web console](https://developer.mozilla.org/en-US/docs/Tools/Web_Console).

This page was loaded in a new process due to a `Large-Allocation` header.  
This message means that the browser saw the `Large-Allocation` header, and was able to reload the page into a new process which should have more available contiguous memory.

A `Large-Allocation` header was ignored due to the load being triggered by a non-GET request.  
When a [`POST`](../methods/post) request is used to load a document, that load cannot currently be redirected into a new process. This error is displayed when loading a document with a `Large-Allocation` header with a non-GET HTTP method. This could be caused due to the document being loaded by a form submission, for example.

A `Large-Allocation` header was ignored due to the presence of windows which have a reference to this browsing context through the frame hierarchy or [`window.opener`](https://developer.mozilla.org/en-US/docs/Web/API/Window/opener).  
This error means that the document was not loaded at the top level of an user-opened or noopener-opened tab or window. It can occur in these situations:

-   The document with the `Large-Allocation` header was loaded in an [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe). Firefox cannot move an iframe into a new process currently, so the document must load in the current process.
-   The document with the `Large-Allocation` header was loaded in a window which was opened by [`window.open()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/open), `<a target="_blank">` or other similar methods without `rel="noopener"` or the `"noopener"` feature being set. These windows must remain in the same process as their opener, as they can communicate, meaning that we cannot allow them to switch processes.
-   The document with the `Large-Allocation header` has opened another window with [`window.open()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/open), `<a target="_blank">` or other similar methods without `rel="noopener"` or the `"noopener"` feature being set. This is for the same reason as above, namely that they can communicate and thus we cannot allow them to switch processes.

A `Large-Allocation` header was ignored due to the document not being loaded out of process.  
Firefox has moved to a [multiprocess architecture](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Multiprocess_Firefox), and this architecture is required in order to support the `Large-Allocation` header. Some [legacy Addons](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/SDK) can prevent Firefox from using this new, faster, multiprocess architecture. If you have one of these Addons installed, then we will continue to use the old single process architecuture for compatibility, and cannot handle the `Large-Allocation` header.

This page would be loaded in a new process due to a `Large-Allocation` header, however `Large-Allocation` process creation is disabled on non-Win32 platforms.  
Firefox currently only supports the `Large-Allocation` header in our 32-bit Windows builds, as memory fragmentation is not an issue in 64-bit builds. If you are running a non-win32 version of Firefox, this error will appear. This check can be disabled with the "dom.largeAllocation.

forceEnable" boolean preferece in about:config.

Specifications
--------------

Not part of any current specifications. An explainer of the ideas behind this header can be found in [this document](https://gist.github.com/mystor/5739e222e398efc6c29108be55eb6fe3).

Browser compatibility<a href="https://github.com/mdn/browser-compat-data" class="bc-github-link">Update compatibility data on GitHub</a>
----------------------------------------------------------------------------------------------------------------------------------------

Desktop

<span class="bc-head-txt-label bc-head-icon-chrome">Chrome</span>

<span class="bc-head-txt-label bc-head-icon-edge">Edge</span>

<span class="bc-head-txt-label bc-head-icon-firefox">Firefox</span>

<span class="bc-head-txt-label bc-head-icon-ie">Internet Explorer</span>

<span class="bc-head-txt-label bc-head-icon-opera">Opera</span>

<span class="bc-head-txt-label bc-head-icon-safari">Safari</span>

`Large-Allocation`

No

No

53

No

No

No

Mobile

<span class="bc-head-txt-label bc-head-icon-webview_android">Android webview</span>

<span class="bc-head-txt-label bc-head-icon-chrome_android">Chrome for Android</span>

<span class="bc-head-txt-label bc-head-icon-firefox_android">Firefox for Android</span>

<span class="bc-head-txt-label bc-head-icon-opera_android">Opera for Android</span>

<span class="bc-head-txt-label bc-head-icon-safari_ios">Safari on iOS</span>

<span class="bc-head-txt-label bc-head-icon-samsunginternet_android">Samsung Internet</span>

`Large-Allocation`

No

No

No

No

No

No

See also
--------

-   [WebAssembly](https://developer.mozilla.org/en-US/docs/WebAssembly)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Large-Allocation$edit" class="_attribution-link">Edit this page on MDN</a>

© 2005–2020 Mozilla and individual contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Large-Allocation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Large-Allocation</a>
