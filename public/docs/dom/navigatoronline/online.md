Navigator.onLine
================

Returns the online status of the browser. The property returns a boolean value, with `true` meaning online and `false` meaning offline. The property sends updates whenever the browser's ability to connect to the network changes. The update occurs when the user follows links or when a script requests a remote page. For example, the property should return `false` when users click links soon after they lose internet connection.

Browsers implement this property differently.

In Chrome and Safari, if the browser is not able to connect to a local area network (LAN) or a router, it is offline; all other conditions return `true`. So while you can assume that the browser is offline when it returns a `false` value, you cannot assume that a true value necessarily means that the browser can access the internet. You could be getting false positives, such as in cases where the computer is running a virtualization software that has virtual ethernet adapters that are always "connected." Therefore, if you really want to determine the online status of the browser, you should develop additional means for checking. To learn more, see the HTML5 Rocks article, [Working Off the Grid](https://www.html5rocks.com/en/mobile/workingoffthegrid.html).

In Firefox and Internet Explorer, switching the browser to offline mode sends a `false` value. Until Firefox 41, all other conditions return a `true` value; testing actual behavior on Nightly 68 on Windows shows that it only looks for LAN connection like Chrome and Safari giving false positives.

You can see changes in the network state by listening for the events on [`window.ononline`](../document/ononline) and [`window.onoffline`](../document/onoffline).

Syntax
------

    online = window.navigator.onLine;

### Value

`online` is a boolean `true` or `false`.

Examples
--------

### Basic usage

To check if you are online, query `window.navigator.onLine`, as in the following example:

    if (navigator.onLine) {
      console.log('online');
    } else {
      console.log('offline');
    }

If the browser doesn't support `navigator.onLine` the above example will always come out as `false`/`undefined`.

### Listening for changes in network status

To see changes in the network state, use `addEventListener` to listen for the events on `window.online` and `window.offline`, as in the following example:

    window.addEventListener('offline', function(e) { console.log('offline'); });

    window.addEventListener('online', function(e) { console.log('online'); });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/browsers.html#dom-navigator-online">HTML Living Standard<br />
<span class="small">The definition of 'navigator.onLine' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`onLine`

1

Earlier versions of Chrome incorrectly return true when a tab is first opened, but it starts reporting the correct connectivity status after the first network event. Windows: 11, Mac: 14, Chrome OS: 13, Linux: Always returns `true`. For history, see [crbug.com/7469](https://crbug.com/7469).

12

1.5

Since Firefox 4 the browser returns `true` when 'Work Offline' mode is disabled and `false` when it is enabled, regardless of actual connectivity. Since Firefox 41, on OS X and Windows, the returned values follow the actual network connectivity, unless 'Work offline' mode is selected (where it will always return `false`).

4

in Internet Explorer 8 'online' and 'offline' events are raised on the `document.body`; under IE 9 they are raised on both `document.body` and `window`.

3

From Opera 11.1 until Opera 12.1, the browser returns `true` when 'Work Offline' mode is disabled and `false` when it is enabled, regardless of actual connectivity.

4

1

Faulty in a WebView component, see Issue [bug 16760](http://code.google.com/p/android/issues/detail?id=16760).

18

4

10.1

From Opera 11.1 until Opera 12.1, the browser returns `true` when 'Work Offline' mode is disabled and `false` when it is enabled, regardless of actual connectivity.

3.2

1.0

Notes
-----

See [Online/Offline Events](online_and_offline_events) for a more detailed description of this property as well as new offline-related features introduced in Firefox 3.

See also
--------

-   [HTML5 Rocks: Working Off the Grid With HTML5 Offline](https://www.html5rocks.com/en/mobile/workingoffthegrid.html)
-   [HTML5 Rocks: "Offline": What does it mean and why should I care?](https://www.html5rocks.com/en/tutorials/offline/whats-offline/)
-   [Mozilla Blog: Offline Web Applications](https://hacks.mozilla.org/2010/01/offline-web-applications/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine/onLine" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorOnLine/onLine</a>
