Using the Storage Access API
============================

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The [Storage Access API](../storage_access_api) should be used by embedded cross-origin documents to verify whether they have access to their first-party storage and, if not, to request access. We’ll briefly look at a common storage access scenario.

Usage notes
-----------

The Storage Access API is designed to allow embedded content to request access to storage that would otherwise be blocked when a user’s browser is set to block all third-party cookies. Since embedded content won’t know which storage policy is in use by the user, it’s best to always check whether the embedded frame has storage access before attempting to read or write from storage. This is particularly true for [`Document.cookie`](../document/cookie) access, as browsers will often return an empty cookie jar when third-party cookies are blocked.

Accessing a user's cookies in an embedded cross-origin iframe
-------------------------------------------------------------

In this example we show how an embedded cross-origin [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) can access a user’s cookies under a storage access policy that blocks third-party cookies.

First of all, if the `<iframe>` is sandboxed, the embedding website needs to add the `allow-storage-access-by-user-activation` [sandbox token](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-sandbox) to allow storage access requests to be successful, along with `allow-scripts` and `allow-same-origin` to allow it to call the API, and execute in an origin that can have cookies:

    <iframe sandbox="allow-storage-access-by-user-activation
                     allow-scripts
                     allow-same-origin">
      ...
    </iframe>

Now on to the code executed inside the embedded document. Since it does not know whether it currently has access to storage, it should first call [`Document.hasStorageAccess()`](../document/hasstorageaccess). If that call returns `false`, we can then call [`Document.requestStorageAccess()`](../document/requeststorageaccess), returning the result so that then we can chain it onto the previous promise call. In the final `then`, we'll have first-party storage access.

    document.hasStorageAccess().then(hasAccess => {
      if (!hasAccess) {
        return document.requestStorageAccess();
      }
    }).then(_ => {
      // Now we have first-party storage access!

      // Let's access some items from the first-party cookie jar
      document.cookie = "foo=bar";              // set a cookie
      localStorage.setItem("username", "John"); // access a localStorage entry
    }).catch(_ => {
      // error obtaining storage access.
    });

Note that access requests are automatically denied unless the embedded content is currently processing a user gesture such as a tap or click — so this code needs to be run inside some kind of user gesture-based event handler, for example:

    btn.addEventListener('click', () => {
      // run code here
    });

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Storage_Access_API/Using" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Storage_Access_API/Using</a>
