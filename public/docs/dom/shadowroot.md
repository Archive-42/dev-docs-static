ShadowRoot
==========

The `ShadowRoot` interface of the Shadow DOM API is the root node of a DOM subtree that is rendered separately from a document's main DOM tree.

You can retrieve a reference to an element's shadow root using its [`Element.shadowRoot`](element/shadowroot) property, provided it was created using [`Element.attachShadow()`](element/attachshadow) with the `mode` option set to `open`.

Properties
----------

 [`ShadowRoot.activeElement`](shadowroot/activeelement) <span class="badge inline readonly">Read only </span>   
Returns the [`Element`](element) within the shadow tree that has focus.

 [`ShadowRoot.delegatesFocus`](shadowroot/delegatesfocus) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns a boolean that indicates whether delegatesFocus was set when the shadow was attached (see [`Element.attachShadow()`](element/attachshadow)).

 [`ShadowRoot.fullscreenElement`](shadowroot/fullscreenelement) <span class="badge inline readonly">Read only </span>   
The element that's currently in full screen mode for this shadow tree.

 [`ShadowRoot.host`](shadowroot/host) <span class="badge inline readonly">Read only </span>   
Returns a reference to the DOM element the `ShadowRoot` is attached to.

 [`ShadowRoot.innerHTML`](shadowroot/innerhtml) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Sets or returns a reference to the DOM tree inside the `ShadowRoot`.

 [`ShadowRoot.mode`](shadowroot/mode) <span class="badge inline readonly">Read only </span>   
The mode of the `ShadowRoot` — either `open` or `closed`. This defines whether or not the shadow root's internal features are accessible from JavaScript.

 [`ShadowRoot.pictureInPictureElement`](shadowroot/pictureinpictureelement) <span class="badge inline readonly">Read only </span>   
Returns the [`Element`](element) within the shadow tree that is currently being presented in picture-in-picture mode.

 [`ShadowRoot.pointerLockElement`](shadowroot/pointerlockelement) <span class="badge inline readonly">Read only </span>   
Returns the [`Element`](element) set as the target for mouse events while the pointer is locked. `null` if lock is pending, pointer is unlocked, or if the target is in another tree.

 [`ShadowRoot.styleSheets`](shadowroot/stylesheets) <span class="badge inline readonly">Read only </span>   
Returns a [`StyleSheetList`](stylesheetlist) of [`CSSStyleSheet`](cssstylesheet) objects for stylesheets explicitly linked into, or embedded in a shadow tree.

Methods
-------

[`ShadowRoot.getAnimations()`](shadowroot/getanimations)  
Returns an array of all [`Animation`](animation) objects currently in effect, whose target elements are descendants of the shadow tree.

<span class="page-not-created">`ShadowRoot.getSelection()`</span>  
Returns a [`Selection`](selection) object representing the range of text selected by the user, or the current position of the caret.

<span class="page-not-created">`ShadowRoot.elementFromPoint()`</span>  
Returns the topmost element at the specified coordinates.

<span class="page-not-created">`ShadowRoot.elementsFromPoint()`</span>  
Returns an array of all elements at the specified coordinates.

Examples
--------

The following snippets are taken from our [life-cycle-callbacks](https://github.com/mdn/web-components-examples/tree/master/life-cycle-callbacks) example ([see it live also](https://mdn.github.io/web-components-examples/life-cycle-callbacks)), which creates an element that displays a square of a size and color specified in the element's attributes.

Inside the `<custom-square>` element's class definition we include some life cycle callbacks that make a call to an external function, `updateStyle()`, which actually applies the size and color to the element. You'll see that we are passing it `this` (the custom element itself) as a parameter.

    connectedCallback() {
      console.log('Custom square element added to page.');
      updateStyle(this);
    }

    attributeChangedCallback(name, oldValue, newValue) {
      console.log('Custom square element attributes changed.');
      updateStyle(this);
    }

In the `updateStyle()` function itself, we get a reference to the shadow DOM using [`Element.shadowRoot`](element/shadowroot). From here we use standard DOM traversal techniques to find the [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) element inside the shadow DOM and then update the CSS found inside it:

    function updateStyle(elem) {
      var shadow = elem.shadowRoot;
      var childNodes = shadow.childNodes;
      for(var i = 0; i < childNodes.length; i++) {
        if(childNodes[i].nodeName === 'STYLE') {
          childNodes[i].textContent =
            'div {' +
              'width: ' + elem.getAttribute('l') + 'px;' +
              'height: ' + elem.getAttribute('l') + 'px;' +
              'background-color: ' + elem.getAttribute('c') + ';' +
            '}';
        }
      }
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#interface-shadowroot">DOM<br />
<span class="small">The definition of 'Interface ShadowRoot' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`ShadowRoot`

53

79

63

No

40

10.1

53

53

63

41

10.3

6.0

`delegatesFocus`

53

79

?

No

40

No

53

53

?

41

No

6.0

`getSelection`

53

79

No

No

40

No

53

53

No

41

No

6.0

`host`

53

79

63

No

40

10.1

53

53

63

41

10.3

6.0

`innerHTML`

53

79

63

No

40

10.1

53

53

63

41

10.3

6.0

`mode`

53

79

63

No

40

10.1

53

53

63

41

10.3

6.0

`activeElement`

53

79

63

No

40

10.1

53

53

63

41

10.3

6.0

`adoptedStyleSheets`

73

79

No

No

60

No

73

73

No

50

No

11.0

`elementFromPoint`

53

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

79

63

No

40

Before Opera 53, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

10.1

53

Before WebView 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

53

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

63

41

Before Opera Android 47, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

10.3

6.0

Before Samsung Internet 9.0, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

`elementsFromPoint`

53

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

79

63

No

40

11.1

53

Before WebView 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

53

Before Chrome 66, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

63

41

11.3

6.0

Before Samsung Internet 9.0, this method returned `null` when the element was a child of a host node. See [issue 759947](https://crbug.com/759947).

`fullscreenElement`

71

79

64

63

No

58

No

71

71

64

63

50

No

10.0

`getAnimations`

84

83

84

83

75

72-75

No

70

69

14

84

84

83

79

60

14

14.0

`pictureInPictureElement`

69

79

No

No

56

13.1

No

No

No

No

13.4

No

`pointerLockElement`

53

79

63

No

40

10.1

53

53

63

41

No

6.0

`styleSheets`

53

79

63

No

40

12.1

53

53

63

41

12.2

6.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/ShadowRoot</a>
