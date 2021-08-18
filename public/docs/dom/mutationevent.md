MutationEvent
=============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Note**

[Mutation Events](https://www.w3.org/TR/DOM-Level-3-Events/#events-mutationevents) (W3C DOM Level 3 Events) have been deprecated in favor of [Mutation Observers](mutationobserver) (W3C DOM4).

The `MutationEvent` interface provides event properties that are specific to modifications to the Document Object Model (DOM) hierarchy and nodes.

Preface
-------

The mutation events have been marked as deprecated in [the DOM Events specification](https://www.w3.org/TR/DOM-Level-3-Events/#events-mutationevents), as the API's design is flawed (see details in the "DOM Mutation Events Replacement: The Story So Far / Existing Points of Consensus" post to [public-webapps](https://lists.w3.org/Archives/Public/public-webapps/2011JulSep/0779.html)).

[Mutation Observers](mutationobserver) have replaced mutation events in DOM4. They have been supported in [most popular browsers for some years](mutationobserver#browser_compatibility).

In addition, mutation events should be avoided because they have **performance issues** and **poor cross-browser support** (as described in the following sections).

### Performance

Adding DOM mutation listeners to a document [profoundly degrades the performance](https://groups.google.com/group/mozilla.dev.platform/browse_thread/thread/2f42f1d75bb906fb?pli=1) of further DOM modifications to that document (making them 1.5 - 7 times slower!). Moreover, removing the listeners does not reverse the damage.

The performance effect is [limited to the documents that have the mutation event listeners](https://groups.google.com/forum/#!topic/mozilla.dev.platform/UH2VqFQRTDA).

### Cross-browser support

These events are not implemented consistently across different browsers, for example:

-   IE prior to version 9 didn't support the mutation events at all and does not implement some of them correctly in version 9 ([for example, DOMNodeInserted](http://help.dottoro.com/ljmcxjla.php))
-   WebKit doesn't support DOMAttrModified (see [webkit bug 8191](https://bugs.webkit.org/show_bug.cgi?id=8191) and [the workaround](https://engineering.silk.co/post/31921750832/mutation-events-what-happens))
-   "mutation name events", i.e. DOMElementNameChanged and DOMAttributeNameChanged are not supported in Firefox (as of version 11), and probably in other browsers as well.
-   ...

Dottoro [documents browser support for mutation events](http://help.dottoro.com/ljfvvdnm.php#additionalEvents).

Mutation events list
--------------------

The following is a list of all mutation events, as defined in [DOM Level 3 Events specification](https://www.w3.org/TR/DOM-Level-3-Events/#events-mutationevents):

-   `DOMAttrModified`
-   `DOMAttributeNameChanged`
-   `DOMCharacterDataModified`
-   `DOMElementNameChanged`
-   `DOMNodeInserted`
-   `DOMNodeInsertedIntoDocument`
-   `DOMNodeRemoved`
-   `DOMNodeRemovedFromDocument`
-   `DOMSubtreeModified`

Usage
-----

You can register a listener for mutation events using [`EventTarget.addEventListener()`](eventtarget/addeventlistener) as follows:

    element.addEventListener("DOMNodeInserted", function (event) {
      // ...
    }, false);

The event object is passed to the listener in a `MutationEvent` (see [its definition in the specification](https://www.w3.org/TR/DOM-Level-3-Events/#events-MutationEvent)) for most events, and <span class="page-not-created">`MutationNameEvent`</span> for `DOMAttributeNameChanged` and `DOMElementNameChanged`.

Browser compatibility
---------------------

No compatibility data found for `api.MutationEvent`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   <span class="page-not-created">`MutationNameEvent`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MutationEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MutationEvent</a>
