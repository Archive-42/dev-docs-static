HTMLElement
===========

The `HTMLElement` interface represents any [HTML](https://developer.mozilla.org/en-US/docs/Web/HTML) element. Some elements directly implement this interface, while others implement it via an interface that inherits it.

Properties
----------

*Inherits properties from its parent, [`Element`](element), and implements those from <span class="page-not-created">`DocumentAndElementEventHandlers`</span>, [`ElementCSSInlineStyle`](elementcssinlinestyle), [`GlobalEventHandlers`](globaleventhandlers), [`HTMLOrForeignElement`](htmlorforeignelement) and <span class="page-not-created">`TouchEventHandlers`</span>.*

[`HTMLElement.accessKey`](htmlelement/accesskey)  
Is a [`DOMString`](domstring) representing the access key assigned to the element.

 [`HTMLElement.accessKeyLabel`](htmlelement/accesskeylabel) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMString`](domstring) containing the element's assigned access key.

[`HTMLElement.contentEditable`](htmlelement/contenteditable)  
Is a [`DOMString`](domstring), where a value of `true` means the element is editable and a value of `false` means it isn't.

 [`HTMLElement.isContentEditable`](htmlelement/iscontenteditable) <span class="badge inline readonly">Read only </span>   
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether or not the content of the element can be edited.

 [`HTMLElement.contextMenu`](htmlelement/contextmenu) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`HTMLMenuElement`](htmlmenuelement) representing the contextual menu associated with the element. It may be `null`.

 [`HTMLOrForeignElement.dataset`](htmlorforeignelement/dataset) <span class="badge inline readonly">Read only </span>   
Returns a [`DOMStringMap`](domstringmap) with which script can read and write the element's [custom data attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes) (`data-*`) .

[`HTMLElement.dir`](htmlelement/dir)  
Is a [`DOMString`](domstring), reflecting the `dir` global attribute, representing the directionality of the element. Possible values are `"ltr"`, `"rtl"`, and `"auto"`.

<span class="page-not-created">`HTMLElement.draggable`</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element can be dragged.

[`HTMLElement.enterkeyhint`](htmlelement/enterkeyhint)  
Is a <span class="page-not-created">`DOMString`</span> defining what action label (or icon) to present for the enter key on virtual keyboards.

[`HTMLElement.hidden`](htmlelement/hidden)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element is hidden or not.

[`HTMLElement.inert`](htmlelement/inert)  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether the user agent must act as though the given node is absent for the purposes of user interaction events, in-page text searches ("find in page"), and text selection.

[`HTMLElement.innerText`](htmlelement/innertext)  
Represents the "rendered" text content of a node and its descendants. As a getter, it approximates the text the user would get if they highlighted the contents of the element with the cursor and then copied it to the clipboard.

 <span class="page-not-created">`HTMLElement.itemScope`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) representing the item scope.

 <span class="page-not-created">`HTMLElement.itemType`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a <span class="page-not-created">`DOMSettableTokenList`</span>…

 <span class="page-not-created">`HTMLElement.itemId`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is a [`DOMString`](domstring) representing the item ID.

 <span class="page-not-created">`HTMLElement.itemRef`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a <span class="page-not-created">`DOMSettableTokenList`</span>…

 <span class="page-not-created">`HTMLElement.itemProp`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a <span class="page-not-created">`DOMSettableTokenList`</span>…

 <span class="page-not-created">`HTMLElement.itemValue`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object) representing the item value.

[`HTMLElement.lang`](htmlelement/lang)  
Is a [`DOMString`](domstring) representing the language of an element's attributes, text, and element contents.

<span class="page-not-created">`HTMLElement.noModule`</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether an import script can be executed in user agents that support module scripts.

[`HTMLOrForeignElement.nonce`](htmlorforeignelement/nonce)  
Returns the cryptographic number used once that is used by Content Security Policy to determine whether a given fetch will be allowed to proceed.

 [`HTMLElement.offsetHeight`](htmlelement/offsetheight) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a `double` containing the height of an element, relative to the layout.

 [`HTMLElement.offsetLeft`](htmlelement/offsetleft) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a `double`, the distance from this element's left border to its `offsetParent`'s left border.

 [`HTMLElement.offsetParent`](htmlelement/offsetparent) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a [`Element`](element) that is the element from which all offset calculations are currently computed.

 [`HTMLElement.offsetTop`](htmlelement/offsettop) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a `double`, the distance from this element's top border to its `offsetParent`'s top border.

 [`HTMLElement.offsetWidth`](htmlelement/offsetwidth) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a `double` containing the width of an element, relative to the layout.

 <span class="page-not-created">`HTMLElement.properties`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span><span class="badge inline readonly">Read only </span>   
Returns a <span class="page-not-created">`HTMLPropertiesCollection`</span>…

<span class="page-not-created">`HTMLElement.spellcheck`</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that controls [spell-checking](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/spellcheck). It is present on all HTML elements, though it doesn't have an effect on all of them.

[`ElementCSSInlineStyle.style`](elementcssinlinestyle/style)  
Is a [`CSSStyleDeclaration`](cssstyledeclaration), an object representing the declarations of an element's style attributes.

[`HTMLOrForeignElement.tabIndex`](htmlorforeignelement/tabindex)  
Is a `long` representing the position of the element in the tabbing order.

[`HTMLElement.title`](htmlelement/title)  
Is a [`DOMString`](domstring) containing the text that appears in a popup box when mouse is over the element.

 <span class="page-not-created">`HTMLElement.translate`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) representing the translation.

### Event handlers

Most event handler properties, of the form `onXYZ`, are defined on the <span class="page-not-created">`DocumentAndElementEventHandlers`</span>, [`GlobalEventHandlers`](globaleventhandlers) or <span class="page-not-created">`TouchEventHandlers`</span> interfaces and implemented by `HTMLElement`. In addition, the following handlers are specific to `HTMLElement`.

 [`HTMLElement.oncopy`](htmlelement/oncopy) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the event handling code for the `copy` event ([bug 280959](https://bugzilla.mozilla.org/show_bug.cgi?id=280959)).

 [`HTMLElement.oncut`](htmlelement/oncut) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the event handling code for the `cut` event ([bug 280959](https://bugzilla.mozilla.org/show_bug.cgi?id=280959)).

 [`HTMLElement.onpaste`](htmlelement/onpaste) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the event handling code for the `paste` event ([bug 280959](https://bugzilla.mozilla.org/show_bug.cgi?id=280959)).

 <span class="page-not-created">`TouchEventHandlers.ontouchstart`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the event handling code for the [`touchstart`](element/touchstart_event) event.

 <span class="page-not-created">`TouchEventHandlers.ontouchend`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the event handling code for the [`touchend`](element/touchend_event) event.

 <span class="page-not-created">`TouchEventHandlers.ontouchmove`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the event handling code for the [`touchmove`](element/touchmove_event) event.

 <span class="page-not-created">`TouchEventHandlers.ontouchenter`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the event handling code for the `touchenter` event.

 <span class="page-not-created">`TouchEventHandlers.ontouchleave`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the event handling code for the `touchleave` event.

 <span class="page-not-created">`TouchEventHandlers.ontouchcancel`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the event handling code for the [`touchcancel`](element/touchcancel_event) event.

Methods
-------

*Inherits methods from its parent, [`Element`](element), and implements those from <span class="page-not-created">`DocumentAndElementEventHandlers`</span>, [`ElementCSSInlineStyle`](elementcssinlinestyle), [`GlobalEventHandlers`](globaleventhandlers), [`HTMLOrForeignElement`](htmlorforeignelement) and <span class="page-not-created">`TouchEventHandlers`</span>.*

 <span class="page-not-created">`HTMLElement.attachInternals()`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Attaches an <span class="page-not-created">`ElementInternals`</span> instance to the custom element.

[`HTMLOrForeignElement.blur()`](htmlorforeignelement/blur)  
Removes keyboard focus from the currently focused element.

[`HTMLElement.click()`](htmlelement/click)  
Sends a mouse click event to the element.

[`HTMLOrForeignElement.focus()`](htmlorforeignelement/focus)  
Makes the element the current keyboard focus.

 [`HTMLElement.forceSpellCheck()`](htmlelement/forcespellcheck) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Runs the spell checker on the element's contents.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`invalid`](htmlinputelement/invalid_event)  
Fired when an element does not satisfy its constraints during constraint validation.  
Also available via the [`oninvalid`](globaleventhandlers/oninvalid) property.

### Animation events

[`animationcancel`](htmlelement/animationcancel_event)  
Fired when an animation unexpectedly aborts.  
Also available via the [`onanimationcancel`](globaleventhandlers/onanimationcancel) property.

[`animationend`](htmlelement/animationend_event)  
Fired when an animation has completed normally.  
Also available via the [`onanimationend`](globaleventhandlers/onanimationend) property.

[`animationiteration`](htmlelement/animationiteration_event)  
Fired when an animation iteration has completed.  
Also available via the [`onanimationiteration`](globaleventhandlers/onanimationiteration) property.

[`animationstart`](htmlelement/animationstart_event)  
Fired when an animation starts.  
Also available via the [`onanimationstart`](globaleventhandlers/onanimationstart) property.

### Input events

[`beforeinput`](htmlelement/beforeinput_event)  
Fired when the value of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element is about to be modified.

[`input`](htmlelement/input_event)  
Fired when the `value` of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element has been changed.  
Also available via the [`oninput`](globaleventhandlers/oninput) property.

[`change`](htmlelement/change_event)  
Fired when the `value` of an [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input), [`<select>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/select), or [`<textarea>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/textarea) element has been changed and committed by the user. Unlike the [`input`](htmlelement/input_event) event, the `change` event is not necessarily fired for each alteration to an element's `value`.

### Pointer events

[`gotpointercapture`](htmlelement/gotpointercapture_event)  
Fired when an element captures a pointer using [`setPointerCapture()`](element/setpointercapture).  
Also available via the [`ongotpointercapture`](globaleventhandlers/ongotpointercapture) property.

[`lostpointercapture`](htmlelement/lostpointercapture_event)  
Fired when a [captured pointer](pointer_events#pointer_capture) is released.  
Also available via the [`onlostpointercapture`](globaleventhandlers/onlostpointercapture) property.

[`pointercancel`](htmlelement/pointercancel_event)  
Fired when a pointer event is canceled.  
Also available via the [`onpointercancel`](globaleventhandlers/onpointercancel) property.

[`pointerdown`](htmlelement/pointerdown_event)  
Fired when a pointer becomes active.  
Also available via the [`onpointerdown`](globaleventhandlers/onpointerdown) property.

[`pointerenter`](htmlelement/pointerenter_event)  
Fired when a pointer is moved into the hit test boundaries of an element or one of its descendants.  
Also available via the [`onpointerenter`](globaleventhandlers/onpointerenter) property.

[`pointerleave`](htmlelement/pointerleave_event)  
Fired when a pointer is moved out of the hit test boundaries of an element.  
Also available via the [`onpointerleave`](globaleventhandlers/onpointerleave) property.

[`pointermove`](htmlelement/pointermove_event)  
Fired when a pointer changes coordinates.  
Also available via the [`onpointermove`](globaleventhandlers/onpointermove) property.

[`pointerout`](htmlelement/pointerout_event)  
Fired when a pointer is moved out of the *hit test* boundaries of an element (among other reasons).  
Also available via the [`onpointerout`](globaleventhandlers/onpointerout) property.

[`pointerover`](htmlelement/pointerover_event)  
Fired when a pointer is moved into an element's hit test boundaries.  
Also available via the [`onpointerover`](globaleventhandlers/onpointerover) property.

[`pointerup`](htmlelement/pointerup_event)  
Fired when a pointer is no longer active.  
Also available via the [`onpointerup`](globaleventhandlers/onpointerup) property.

### Transition events

[`transitioncancel`](htmlelement/transitioncancel_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is canceled.  
Also available via the [`ontransitioncancel`](globaleventhandlers/ontransitioncancel) property.

[`transitionend`](htmlelement/transitionend_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has completed.  
Also available via the [`ontransitionend`](globaleventhandlers/ontransitionend) property.

[`transitionrun`](htmlelement/transitionrun_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is first created.  
Also available via the <span class="page-not-created">`ontransitionrun`</span> property.

[`transitionstart`](htmlelement/transitionstart_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has actually started.  
Also available via the <span class="page-not-created">`ontransitionstart`</span> property.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#extensions-to-the-htmlelement-interface">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'HTMLElement' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the following properties: <code>offsetParent</code>, <code>offsetTop</code>, <code>offsetLeft</code>, <code>offsetWidth</code>, and <code>offsetHeight</code>.</td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/elements.html#htmlelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the following properties: <code>translate</code>, <code>itemScope</code>, <code>itemType</code>, <code>itemId</code>, <code>itemRef</code>, <code>itemProp</code>, <code>properties</code>, and <code>itemValue</code>.<br />
Added the following method: <code>forceSpellcheck()</code>.<br />
Moved the <code>onXYZ</code> attributes to the <a href="globaleventhandlers"><code>GlobalEventHandlers</code></a> interface and added an inheritance from it.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/dom.html#htmlelement">HTML5<br />
<span class="small">The definition of 'HTMLElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the following properties: <code>dataset</code>, <code>hidden</code>, <code>tabIndex</code>, <code>accessKey</code>, <code>accessKeyLabel</code>, <code>draggable</code>, <code>dropzone</code>, <code>contentEditable</code>, <code>isContentEditable</code>, <code>contextMenu</code>, <code>spellcheck</code>, <code>commandType</code>, <code>commandLabel</code>, <code>commandIcon</code>, <code>commandHidden</code>, <code>commandDisabled</code>, <code>commandChecked</code>, <code>style</code>, and all the <code>onXYZ</code> properties.<br />
Moved the <code>id</code> and <code>className</code> properties to the <a href="element"><code>Element</code></a> interface.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-011100101">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-HTML/">Document Object Model (DOM) Level 2 HTML Specification</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-011100101">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLElement`

1

12

1

5.5

8

1.3

1

18

4

10.1

1

1.0

`accessKey`

17

12

5

5.5

≤12.1

6

4.4

18

5

≤12.1

6

1.0

`accessKeyLabel`

No

No

8

No

No

14

No

No

8

No

14

No

`animationcancel_event`

No

No

54

No

No

13.1

12

No

No

54

No

13.4

12

No

`animationend_event`

43

12

Yes

10

30

9

43

43

Yes

30

9

4.0

`animationiteration_event`

43

12

51

10

30

9

43

43

51

30

9

4.0

`animationstart_event`

43

12

51

10

30

9

43

43

51

30

9

4.0

`attachInternals`

77

79

No

No

64

No

77

77

No

55

No

12.0

`autocapitalize`

66

79

83

No

53

No

66

66

83

47

10.3

9.0

`beforeinput_event`

Yes

79

87

74-87

No

Yes

Yes

Yes

Yes

87

79-87

Yes

Yes

Yes

`blur`

1

12

1.5

5.5

8

3

4.4

18

4

10.1

1

1.0

`click`

9

Before Chrome 19, `click()` is only defined on buttons and inputs.

12

3

\["Before Firefox 5, `click()` is only defined on buttons and inputs, and has no effect on text and file inputs.", "Starting in Firefox 75, the `click()` function works even when the element is not attached to a DOM tree."\]

5.5

10.5

6

≤37

Before Android WebView 4.4, `click()` is only defined on buttons and inputs.

18

Before Chrome 19, `click()` is only defined on buttons and inputs.

4

\["Before Firefox 5, `click()` is only defined on buttons and inputs, and has no effect on text and file inputs.", "Starting in Firefox for Android 79, the `click()` function works even when the element is not attached to a DOM tree."\]

11

6

1.0

Before Samsung Internet 1.5, `click()` is only defined on buttons and inputs.

`contentEditable`

1

12

3

5.5

9

3

4.4

18

4

10.1

1

1.0

`contextMenu`

45-61

≤18-79

8

No

No

No

45-61

45-61

8

No

No

5.0-8.0

`dataset`

8

12

6

11

11

5.1

4.4

18

6

11

5

1.0

`dir`

1

12

1

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

`draggable`

3

12

2

10

12

5

4.4

18

4

12

4

1.0

`enterKeyHint`

77

79

79

No

64

13.1

77

77

79

55

13.4

12.0

`focus`

1

12

1.5

5.5

8

3

4.4

18

4

10.1

1

1.0

`forceSpellCheck`

No

No

No

No

No

No

No

No

No

No

No

No

`gotpointercapture_event`

57

≤79

59

?

44

13

57

57

79

43

13

7.0

`hidden`

6

12

1

11

11.6

5.1

≤37

18

4

12

5

1.0

`inert`

60

79

81

No

47

No

No

60

81

44

No

No

`innerText`

1

12

45

5.5

9.6

3

4.4

18

45

10.1

1

1.0

`input_event`

1

79

12-79

Not supported on `select`, `checkbox`, or `radio` inputs.

6

9

Only supports `input` of type `text` and `password`.

11.6

3.1

1

18

6

12

2

1.0

`inputMode`

66

79

77

No

53

12.1

66

66

79

47

12.2

9.0

`isContentEditable`

1

12

4

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

`itemId`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`itemProp`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`itemRef`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`itemScope`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`itemType`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`itemValue`

17-28

No

16-49

No

11-15

No

No

18-28

16-49

11-14

No

1.0-1.5

`lang`

1

12

1

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

`lostpointercapture_event`

57

≤79

59

?

44

13

57

57

79

43

13

7.0

`nonce`

61

79

75

No

48

10

The property is defined only for its useful elements: `<link>`, `<script>`, and `<style>`; it is undefined for all other elements.

61

61

79

45

10

The property is defined only for its useful elements: `<link>`, `<script>`, and `<style>`; it is undefined for all other elements.

8.0

`offsetHeight`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`offsetLeft`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`offsetParent`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`offsetTop`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`offsetWidth`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`oncopy`

1

12

3

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`oncut`

1

12

9

5.5

≤12.1

3

1

18

9

≤12.1

1

1.0

`onpaste`

1

12

9

5.5

≤12.1

3

1

18

9

≤12.1

1

1.0

`outerText`

43

12

No

5.5

≤12.1

1.3

43

43

No

≤12.1

1

4.0

`pointercancel_event`

55

12

12-79

59

29

11

10

42

No

55

55

79

29

42

No

6.0

`pointerdown_event`

55

12

12-79

59

29

11

10

42

No

55

55

79

29

42

No

6.0

`pointerenter_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerleave_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointermove_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerout_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerover_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`pointerup_event`

55

12

12-79

59

29

11

10

42

13

55

55

79

29

42

13

6.0

`spellcheck`

9

12

2

10

≤12.1

5.1

≤37

18

4

≤12.1

5

1.0

`style`

1

12

1

5.5

8

3

1

18

4

10.1

1

1.0

`tabIndex`

1

18

12

Returns incorrect value for elements without an explicit tabindex attribute. See [issue 4365703](https://developer.microsoft.com/microsoft-edge/platform/issues/4365703/) for details.

1

5.5

Returns incorrect value for elements without an explicit tabindex attribute. See [issue 4365703](https://developer.microsoft.com/microsoft-edge/platform/issues/4365703/) for details.

≤12.1

3.1

4.4

18

4

≤12.1

2

1.0

`title`

1

12

1

5.5

≤12.1

3

4.4

18

4

≤12.1

1

1.0

`transitioncancel_event`

74

≤79

53

?

62

13.1

12

74

74

53

53

13.4

12

11.0

`transitionend_event`

26

1

≤79

≤79

51

10

12.1

15

11.6-15

6.1

4

≤37

1

26

18

51

12.1

14

12-14

7

3.2

1.5

1.0

`transitionrun_event`

74

≤79

53

?

62

13.1

12

74

74

53

53

13.4

12

11.0

`transitionstart_event`

74

≤79

53

?

62

13.1

12

74

74

53

53

13.4

12

11.0

`translate`

19

79

No

No

15

6

4.4

25

No

14

6

1.5

See also
--------

-   [`Element`](element)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement</a>
