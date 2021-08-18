# Testing media queries programmatically

The [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) provides features that can test the results of a [media query](../media_queries) programmatically, via the [`MediaQueryList`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList) interface and its methods and properties. Once you've created a `MediaQueryList` object, you can check the result of the query or receive notifications when the result changes.

## Creating a media query list

Before you can evaluate the results of a media query, you need to create the `MediaQueryList` object representing the query. To do this, use the [`window.matchMedia`](https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia) method.

For example, to set up a query list that determines if the device is in landscape or portrait orientation:

    const mediaQueryList = window.matchMedia("(orientation: portrait)");

## Checking the result of a query

Once you've created your media query list, you can check the result of the query by looking at the value of its `matches` property:

    if (mediaQueryList.matches) {
      /* The viewport is currently in portrait orientation */
    } else {
      /* The viewport is not currently in portrait orientation, therefore landscape */
    }

## Receiving query notifications

If you need to be aware of changes to the evaluated result of the query on an ongoing basis, it's more efficient to register a [listener](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) than to poll the query's result. To do this, call the `addListener()` method on the [`MediaQueryList`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList) object, with a callback function to invoke when the media query status changes (e.g., the media query test goes from `true` to `false`):

    // Create the query list.
    const mediaQueryList = window.matchMedia("(orientation: portrait)");

    // Define a callback function for the event listener.
    function handleOrientationChange(mql) {
      // ...
    }

    // Run the orientation change handler once.
    handleOrientationChange(mediaQueryList);

    // Add the callback function as a listener to the query list.
    mediaQueryList.addListener(handleOrientationChange);

This code creates the orientation-testing media query list, then adds an event listener to it. After defining the listener, we also call the listener directly. This makes our listener perform adjustments based on the current device orientation; otherwise, our code might assume the device is in portrait mode at startup, even if it's actually in landscape mode.

The `handleOrientationChange()` function would look at the result of the query and handle whatever we need to do on an orientation change:

    function handleOrientationChange(evt) {
      if (evt.matches) {
        /* The viewport is currently in portrait orientation */
      } else {
        /* The viewport is currently in landscape orientation */
      }
    }

Above, we define the parameter as `evt` — an event object. This makes sense because [newer implementations of `MediaQueryList`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList#browser_compatibility) handle event listeners in a standard way. They no longer use the unusual [`MediaQueryListListener`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList) mechanism, but a standard event listener setup, passing an [event object](https://developer.mozilla.org/en-US/docs/Web/API/Event) of type [`MediaQueryListEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent) as the argument to the callback function.

This event object also includes the [`media`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent/media) and [`matches`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent/matches) properties, so you can query these features of the `MediaQueryList` by directly accessing it, or accessing the event object.

## Ending query notifications

To stop receiving notifications about changes to the value of your media query, call `removeListener()` on the `MediaQueryList`, passing it the name of the previously-defined callback function:

    mediaQueryList.removeListener(handleOrientationChange);

## Browser compatibility

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

`Testing_media_queries`

9

12

6

10

12.1

5.1

Prior to Safari 14, `MediaQueryList` is based on `EventTarget`, so you must use `addListener()` and `removeListener()` to observe media query lists.

≤37

18

6

Yes

5

Prior to Safari 14, `MediaQueryList` is based on `EventTarget`, so you must use `addListener()` and `removeListener()` to observe media query lists.

1.0

`EventListener_objects`

45

≤79

55

No

No

14

45

45

55

No

14

5.0

`EventTarget_inheritance`

45

16

55

No

Yes

14

45

45

55

Yes

14

5.0

`addListener`

9

12

6

10

12.1

5.1

Prior to Safari 14, `MediaQueryList` is based on `EventTarget`, so you must use `addListener()` and `removeListener()` to observe media query lists.

≤37

18

6

Yes

5

Prior to Safari 14, `MediaQueryList` is based on `EventTarget`, so you must use `addListener()` and `removeListener()` to observe media query lists.

1.0

`matches`

9

12

6

10

12.1

5.1

≤37

18

6

Yes

5

1.0

`media`

9

12

6

10

12.1

5.1

≤37

18

6

Yes

5

1.0

`onchange`

45

79

55

No

Yes

14

45

45

55

Yes

14

5.0

`removeListener`

9

12

6

10

12.1

5.1

Prior to Safari 14, `MediaQueryList` is based on `EventTarget`, so you must use `addListener()` and `removeListener()` to observe media query lists.

≤37

18

6

Yes

5

Prior to Safari 14, `MediaQueryList` is based on `EventTarget`, so you must use `addListener()` and `removeListener()` to observe media query lists.

1.0

BCD tables only load in the browser

## See also

- [Media queries](using_media_queries)
- [`window.matchMedia()`](https://developer.mozilla.org/en-US/docs/Web/API/Window/matchMedia)
- [`MediaQueryList`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList)
- [`MediaQueryListEvent`](https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryListEvent)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries</a>
