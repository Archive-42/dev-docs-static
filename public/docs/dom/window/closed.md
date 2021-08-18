Window.closed
=============

The `Window.closed` read-only property indicates whether the referenced window is closed or not.

Syntax
------

    const isClosed = windowRef.closed;

### Value

A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean). Possible values:

-   `true`: The window has been closed.
-   `false`: The window is open.

Examples
--------

### Change the URL of a window from a popup

The following example demonstrates how a popup window can change the URL of the window that opened it. Before attempting to change the URL, it checks that the current window has an opener using the [`window.opener`](opener) property and that the opener isn't closed:

    // Check that an opener exists and is not closed
    if (window.opener && !window.opener.closed) {
      window.opener.location.href = 'http://www.mozilla.org';
    }

Note that popups can only access the window that opened them.

### Refreshing a previously opened popup

In this example the function `refreshPopupWindow()` calls the `reload()` method of the popup's location object to refresh its data. If the popup hasn't been opened yet or the user has closed it a new window is opened.

    const popupWindow = null;

    function refreshPopupWindow() {
      if (popupWindow && !popupWindow.closed) {
        // popupWindow is open, refresh it
        popupWindow.location.reload(true);
      } else {
        // Open a new popup window
        popupWindow = window.open('popup.html', 'dataWindow');
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-window-closed">HTML Living Standard<br />
<span class="small">The definition of 'window.closed' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/closed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/closed</a>
