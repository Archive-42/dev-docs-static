HTMLTrackElement
================

The `HTMLTrackElement` interface represents an [HTML](https://developer.mozilla.org/en-US/docs/Glossary/HTML) [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track) element within the [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM). This element can be used as a child of either [`<audio>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio) or [`<video>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video) to specify a text track containing information such as closed captions or subtitles.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLTrackElement.kind`</span>  
Is a [`DOMString`](domstring) that reflects the [`kind`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track#attr-kind) HTML attribute, indicating how the text track is meant to be used. Possible values are: `subtitles`, `captions`, `descriptions`, `chapters`, or `metadata`.

[`HTMLTrackElement.src`](htmltrackelement/src)  
Is a [`DOMString`](domstring) that reflects the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track#attr-src) HTML attribute, indicating the address of the text track data.

<span class="page-not-created">`HTMLTrackElement.srclang`</span>  
Is a [`DOMString`](domstring) that reflects the [`srclang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track#attr-srclang) HTML attribute, indicating the language of the text track data.

<span class="page-not-created">`HTMLTrackElement.label`</span>  
Is a [`DOMString`](domstring) that reflects the [`label`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track#attr-label) HTML attribute, indicating a user-readable title for the track.

<span class="page-not-created">`HTMLTrackElement.default`</span>  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) reflecting the [`default`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track#attr-default) attribute, indicating that the track is to be enabled if the user's preferences do not indicate that another track would be more appropriate.

 <span class="page-not-created">`HTMLTrackElement.readyState`</span> <span class="badge inline readonly">Read only </span>   
Returns an `unsigned short` that show the readiness state of the track:

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>NONE</code></td><td>0</td><td>Indicates that the text track's cues have not been obtained.</td></tr><tr class="even"><td><code>LOADING</code></td><td>1</td><td>Indicates that the text track is loading and there have been no fatal errors encountered so far. Further cues might still be added to the track by the parser.</td></tr><tr class="odd"><td><code>LOADED</code></td><td>2</td><td>Indicates that the text track has been loaded with no fatal errors.</td></tr><tr class="even"><td><code>ERROR</code></td><td>3</td><td>Indicates that the text track was enabled, but when the user agent attempted to obtain it, this failed in some way. Some or all of the cues are likely missing and will not be obtained.</td></tr></tbody></table>

 <span class="page-not-created">`HTMLTrackElement.track`</span> <span class="badge inline readonly">Read only </span>   
Returns [`TextTrack`](texttrack) is the track element's text track data.

Methods
-------

*No specific method; inherits methods from its parent, [`HTMLElement`](htmlelement).*

Events
------

*The following events may be fired on a [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track) element, in addition to any that may be fired at its parent, [`HTMLElement`](htmlelement).*

[`cuechange`](htmltrackelement/cuechange_event)  
Sent when the underlying [`TextTrack`](texttrack) has changed the currently-presented cues. This event is always sent to the `TextTrack` but is *also* sent to the `HTMLTrackElement` if one is associated with the track.  
You may also use the [`oncuechange`](globaleventhandlers/oncuechange) event handler to establish a handler for this event.

Usage notes
-----------

### Loading of the track's text resource

The WebVTT or TTML data describing the actual cues for the text track isn't loaded if the track's [`mode`](texttrack/mode) is initially in the `disabled` state. If you need to be able to perform any processing on the track after the `<track>` is set up, you should instead ensure that the track's `mode` is either `hidden` (if you don't want it to start out being presented to the user) or `showing` (to initially display the track). You can then change the mode as desired later.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmltrackelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLTrackElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/embedded-content-0.html#the-track-element">HTML5<br />
<span class="small">The definition of 'HTMLTrackElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLTrackElement`

23

12

31

Prior to Firefox 50, text tracks would only load if the element is in a document.

10

12

6

≤37

25

31

Prior to Firefox 50, text tracks would only load if the element is in a document.

12

6

1.5

`cuechange_event`

Yes

≤79

68

No

?

Yes

Yes

Yes

68

?

Yes

Yes

`default`

23

12

31

10

12

6

≤37

25

31

12

6

1.5

`kind`

23

12

31

10

12

6

≤37

25

31

12

6

1.5

`label`

23

12

31

10

12

6

≤37

25

31

12

6

1.5

`readyState`

23

12

31

10

12

6

≤37

25

31

12

6

1.5

`src`

23

12

31

Setting the `src` property did not work properly in versions prior to 50.

10

12

6

≤37

25

31

Setting the `src` property did not work properly in versions prior to 50.

12

6

1.5

`srclang`

23

12

31

10

12

6

≤37

25

31

12

6

1.5

`track`

23

12

31

10

12

6

≤37

25

31

12

6

1.5

See also
--------

-   The HTML element implementing this interface: [`<track>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/track).

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLTrackElement</a>
