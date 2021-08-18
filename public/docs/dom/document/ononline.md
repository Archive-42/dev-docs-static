# Document.ononline

The `Document.online` event is fired on the [`<body>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body) of each page when the browser switches between online and offline mode. Additionally, the events bubble up from `document.body`, to `document`, ending at `window`. Both events are non-cancellable (you can't prevent the user from coming online, or going offline).

`window.navigator.onLine` returns boolean `true` if the browser is online and `false` if it is definitely offline (disconnected from the network). The `online` and `offline` events are fired when the value of this attribute changes.

It is important to note that this event and attribute are inherently unreliable. A computer can be connected to a network without having Internet access.

You can register listeners for these events in a few familiar ways:

- Using [`addEventListener`](../eventtarget/addeventlistener) on the `window`, `document`, or `document.body`
- By setting the `.ononline` or `.onoffline` properties on `document` or `document.body` to a JavaScript `Function` object. (**Note:** using `window.ononline` or `window.onoffline` will not work for compatibility reasons.)
- By specifying `ononline="..."` or `onoffline="..."` attributes on the `<body>` tag in the HTML markup.

## Example

There's [a simple test case](https://bugzilla.mozilla.org/attachment.cgi?id=220609) that you can run to verify that the events are working.

## References

- [Online and offline events \[en-US\]](../navigatoronline/online_and_offline_events)
- [WHATWG Web App Specification](https://www.whatwg.org/specs/web-apps/current-work/#event-online)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/ononline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/ononline</a>
