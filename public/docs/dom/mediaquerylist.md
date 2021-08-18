# MediaQueryList

A `MediaQueryList` object stores information on a [media query](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries) applied to a document, with support for both immediate and event-driven matching against the state of the document. You can create a `MediaQueryList` by calling [`matchMedia()`](window/matchmedia) on the [`window`](window) object. The resulting object handles sending notifications to listeners when the media query state changes (i.e. when the media query test starts or stops evaluating to `true`).

This is very useful for adaptive design, since this makes it possible to observe a document to detect when its media queries change, instead of polling the values periodically, and allows you to programmatically make changes to a document based on media query status.

## Properties

_The `MediaQueryList` interface inherits properties from its parent interface, [`EventTarget`](eventtarget)._

[`matches`](mediaquerylist/matches)<span class="badge inline readonly">Read only </span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that returns `true` if the [`document`](document) currently matches the media query list, or `false` if not.

[`media`](mediaquerylist/media)<span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) representing a serialized media query.

## Methods

_The `MediaQueryList` interface inherits methods from its parent interface, [`EventTarget`](eventtarget)._

[`addListener()`](mediaquerylist/addlistener)<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Adds to the `MediaQueryList` a callback which is invoked whenever the media query status—whether or not the document matches the media queries in the list—changes. This method exists primarily for backward compatibility; if possible, you should instead use [`addEventListener()`](eventtarget/addeventlistener) to watch for the <span class="page-not-created">`change`</span> event.

[`removeListener()`](mediaquerylist/removelistener)<span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Removes the specified listener callback from the callbacks to be invoked when the `MediaQueryList` changes media query status, which happens any time the document switches between matching and not matching the media queries listed in the `MediaQueryList`. This method has been kept for backward compatibility; if possible, you should generally use [`removeEventListener()`](eventtarget/removeeventlistener) to remove change notification callbacks (which should have previously been added using `addEventListener()`).

## Events

_The following events are delivered to `MediaQueryList` objects:_

<span class="page-not-created">`change`</span>  
Sent to the `MediaQueryList` when the result of running the media query against the document changes. For example, if the media query is `(min-width: 400px)`, the `change` event is fired any time the width of the document's [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) changes such that its width moves across the 400px boundary in either direction.  
Also available using the [`onchange`](mediaquerylist/onchange) event handler property.

## Examples

This simple example creates a `MediaQueryList` and then sets up a listener to detect when the media query status changes, running a custom function when it does to change the appearance of the page.

    var para = document.querySelector('p');
    var mql = window.matchMedia('(max-width: 600px)');

    function screenTest(e) {
      if (e.matches) {
        /* the viewport is 600 pixels wide or less */
        para.textContent = 'This is a narrow screen — less than 600px wide.';
        document.body.style.backgroundColor = 'red';
      } else {
        /* the viewport is more than 600 pixels wide */
        para.textContent = 'This is a wide screen — more than 600px wide.';
        document.body.style.backgroundColor = 'blue';
      }
    }

    mql.addEventListener('change', screenTest);

**Note**: You can find this example on GitHub (see the [source code](https://github.com/mdn/dom-examples/blob/master/mediaquerylist/index.html), and also see it [running live](https://mdn.github.io/dom-examples/mediaquerylist/index.html)).

You can find other examples on the individual property and method pages.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#the-mediaquerylist-interface">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'MediaQueryList' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`MediaQueryList`

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

## See also

- [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [Using media queries from code](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Testing_media_queries)
- [`window.matchMedia()`](window/matchmedia)
- [`MediaQueryListEvent`](mediaquerylistevent)
- The article [`Window.devicePixelRatio`](window/devicepixelratio) also has a useful example

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MediaQueryList</a>
