# FontFaceSet

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `FontFaceSet` interface of the [CSS Font Loading API](css_font_loading_api) manages the loading of font-faces and querying of their download status.It is available as document.fonts.

## Properties

<span class="page-not-created">`FontFaceSet.status`</span> <span class="badge inline readonly">Read only </span>  
Indicates the font-face's loading status. It will be one of `'loading'` or `'loaded'`.

[`FontFaceSet.ready`](fontfaceset/ready) <span class="badge inline readonly">Read only </span>  
[`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves once font loading and layout operations have completed.

### Events

<span class="page-not-created">`FontFaceSet.onloading`</span>  
An [`EventListener`](eventlistener) called whenever an event of type `loading` is fired, indicating a font-face set has started loading.

<span class="page-not-created">`FontFaceSet.onloadingdone`</span>  
An [`EventListener`](eventlistener) called whenever an event of type `loadingdone` is fired, indicating that a font face set has finished loading.

<span class="page-not-created">`FontFaceSet.onloadingerror`</span>  
An [`EventListener`](eventlistener) called whenever an event of type `loadingerror` is fired, indicating that an error occurred whilst loading a font-face set.

## Methods

<span class="page-not-created">`FontFaceSet.add()`</span>  
Adds a font to the font set.

[`FontFaceSet.check()`](fontfaceset/check)  
A [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether a font is loaded, but doesn't initiate a load when it isn't.

<span class="page-not-created">`FontFaceSet.clear()`</span>  
Removes all manually-added fonts from the font set. [CSS-connected](https://www.w3.org/TR/css-font-loading-3/#css-connected) fonts are unaffected.

<span class="page-not-created">`FontFaceSet.delete()`</span>  
Removes a manually-added font from the font set. [CSS-connected](https://www.w3.org/TR/css-font-loading-3/#css-connected) fonts are unaffected.

[`FontFaceSet.load()`](fontfaceset/load)  
Returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to a list of font-faces for a requested font.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-font-loading/#FontFaceSet-interface">CSS Font Loading Module Level 3<br />
<span class="small">The definition of 'FontFaceSet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`FontFaceSet`

35

≤79

41

No

Yes

10

37

35

41

Yes

10

4.0

`FontFaceSet`

No

No

No

No

No

10

No

No

No

No

10

No

`add`

48

≤79

Yes

No

35

10

48

48

Yes

35

Yes

5.0

`check`

35

≤79

41

No

?

10

37

35

41

?

Yes

4.0

`clear`

48

≤79

Yes

No

35

10

48

48

Yes

35

Yes

5.0

`delete`

48

≤79

Yes

No

35

10

48

48

Yes

35

Yes

5.0

`entries`

No

No

41

No

No

10

No

No

41

No

10

No

`has`

No

No

41

No

No

10

No

No

41

No

10

No

`keys`

No

No

41

No

No

10

No

No

41

No

10

No

`load`

35

≤79

41

No

35

10

37

35

41

35

Yes

4.0

`onloading`

48

≤79

Yes

No

35

10

48

48

Yes

35

Yes

5.0

`onloadingdone`

48

≤79

Yes

No

35

10

48

48

Yes

35

Yes

5.0

`onloadingerror`

48

≤79

Yes

No

35

10

48

48

Yes

35

Yes

5.0

`ready`

35

≤79

41

No

35

10

37

35

41

35

Yes

4.0

`size`

No

No

41

No

No

10

No

No

41

No

10

No

`status`

48

≤79

Yes

No

35

10

48

48

Yes

35

Yes

5.0

`values`

No

No

41

No

No

10

No

No

41

No

10

No

`worker_support`

69

≤79

?

No

?

?

69

69

?

?

?

10.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FontFaceSet</a>
