# Element

`Element` is the most general base class from which all element objects (i.e. objects that represent elements) in a [`Document`](document) inherit. It only has methods and properties common to all kinds of elements. More specific classes inherit from `Element`. For example, the [`HTMLElement`](htmlelement) interface is the base interface for HTML elements, while the [`SVGElement`](svgelement) interface is the basis for all SVG elements. Most functionality is specified further down the class hierarchy.

Languages outside the realm of the Web platform, like XUL through the `XULElement` interface, also implement `Element`.

## Properties

_`Element` inherits properties from its parent interface, [`Node`](node), and by extension that interface's parent, [`EventTarget`](eventtarget)._

[`Element.assignedSlot`](element/assignedslot)<span class="badge inline readonly">Read only </span>  
Returns a [`HTMLSlotElement`](htmlslotelement) representing the [`<slot>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/slot) the node is inserted in.

[`Element.attributes`](element/attributes) <span class="badge inline readonly">Read only </span>  
Returns a [`NamedNodeMap`](namednodemap) object containing the assigned attributes of the corresponding HTML element.

[`Element.childElementCount`](element/childelementcount) <span class="badge inline readonly">Read only </span>  
Returns the number of child elements of this element.

[`Element.children`](element/children) <span class="badge inline readonly">Read only </span>  
Returns the child elements of this element.

[`Element.classList`](element/classlist) <span class="badge inline readonly">Read only </span>  
Returns a [`DOMTokenList`](domtokenlist) containing the list of class attributes.

[`Element.className`](element/classname)  
Is a [`DOMString`](domstring) representing the class of the element.

[`Element.clientHeight`](element/clientheight) <span class="badge inline readonly">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the inner height of the element.

[`Element.clientLeft`](element/clientleft) <span class="badge inline readonly">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the width of the left border of the element.

[`Element.clientTop`](element/clienttop) <span class="badge inline readonly">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the width of the top border of the element.

[`Element.clientWidth`](element/clientwidth) <span class="badge inline readonly">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the inner width of the element.

[`Element.firstElementChild`](element/firstelementchild) <span class="badge inline readonly">Read only </span>  
Returns the first child element of this element.

[`Element.id`](element/id)  
Is a [`DOMString`](domstring) representing the id of the element.

[`Element.innerHTML`](element/innerhtml)  
Is a [`DOMString`](domstring) representing the markup of the element's content.

[`Element.lastElementChild`](element/lastelementchild) <span class="badge inline readonly">Read only </span>  
Returns the last child element of this element.

[`Element.localName`](element/localname) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) representing the local part of the qualified name of the element.

[`Element.namespaceURI`](element/namespaceuri) <span class="badge inline readonly">Read only </span>  
The namespace URI of the element, or `null` if it is no namespace.

**Note:** In Firefox 3.5 and earlier, HTML elements are in no namespace. In later versions, HTML elements are in the `http://www.w3.org/1999/xhtml` namespace in both HTML and XML trees.

[`Element.nextElementSibling`](element/nextelementsibling) <span class="badge inline readonly">Read only </span>  
Is an [`Element`](element), the element immediately following the given one in the tree, or `null` if there's no sibling node.

[`Element.outerHTML`](element/outerhtml)  
Is a [`DOMString`](domstring) representing the markup of the element including its content. When used as a setter, replaces the element with nodes parsed from the given string.

[`Element.part`](element/part)  
Represents the part identifier(s) of the element (i.e. set using the `part` attribute), returned as a [`DOMTokenList`](domtokenlist).

[`Element.prefix`](element/prefix) <span class="badge inline readonly">Read only </span>  
A [`DOMString`](domstring) representing the namespace prefix of the element, or `null` if no prefix is specified.

[`Element.previousElementSibling`](element/previouselementsibling) <span class="badge inline readonly">Read only </span>  
Is a [`Element`](element), the element immediately preceding the given one in the tree, or `null` if there is no sibling element.

[`Element.scrollHeight`](element/scrollheight) <span class="badge inline readonly">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the scroll view height of an element.

[`Element.scrollLeft`](element/scrollleft)  
Is a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the left scroll offset of the element.

[`Element.scrollLeftMax`](element/scrollleftmax) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the maximum left scroll offset possible for the element.

[`Element.scrollTop`](element/scrolltop)  
A [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing number of pixels the top of the document is scrolled vertically.

[`Element.scrollTopMax`](element/scrolltopmax) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the maximum top scroll offset possible for the element.

[`Element.scrollWidth`](element/scrollwidth) <span class="badge inline readonly">Read only </span>  
Returns a [`Number`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number) representing the scroll view width of the element.

[`Element.shadowRoot`](element/shadowroot)<span class="badge inline readonly">Read only </span>  
Returns the open shadow root that is hosted by the element, or null if no open shadow root is present.

[`Element.openOrClosedShadowRoot`](element/openorclosedshadowroot) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="badge inline readonly">Read only </span>  
Returns the shadow root that is hosted by the element, regardless if its open or closed. **Available only to [WebExtensions](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions).**

[`Element.slot`](element/slot) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns the name of the shadow DOM slot the element is inserted in.

[`Element.tabStop`](element/tabstop) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element can receive input focus via the tab key.

[`Element.tagName`](element/tagname) <span class="badge inline readonly">Read only </span>  
Returns a [`String`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String) with the name of the tag for the given element.

### Properties included from ARIA

_The `Element` interface includes the following properties, defined on the `ARIAMixin` mixin._

[`Element.ariaAtomic`](element/ariaatomic)  
Is a [`DOMString`](domstring) reflecting the `aria-atomic` attribute, which indicates whether assistive technologies will present all, or only parts of, the changed region based on the change notifications defined by the `aria-relevant` attribute.

[`Element.ariaAutoComplete`](element/ariaautocomplete)  
Is a [`DOMString`](domstring) reflecting the `aria-autocomplete` attribute, which indicates whether inputting text could trigger display of one or more predictions of the user's intended value for a combobox, searchbox, or textbox and specifies how predictions would be presented if they were made.

[`Element.ariaBusy`](element/ariabusy)  
Is a [`DOMString`](domstring) reflecting the `aria-busy` attribute, which indicates whether an element is being modified, as assistive technologies may want to wait until the modifications are complete before exposing them to the user.

[`Element.ariaChecked`](element/ariachecked)  
Is a [`DOMString`](domstring) reflecting the `aria-checked` attribute, which indicates the current "checked" state of checkboxes, radio buttons, and other widgets that have a checked state.

[`Element.ariaColCount`](element/ariacolcount)  
Is a [`DOMString`](domstring) reflecting the `aria-colcount` attribute, which defines the number of columns in a table, grid, or treegrid.

[`Element.ariaColIndex`](element/ariacolindex)  
Is a [`DOMString`](domstring) reflecting the `aria-colindex` attribute, which defines an element's column index or position with respect to the total number of columns within a table, grid, or treegrid.

[`Element.ariaColIndexText`](element/ariacolindextext)  
Is a [`DOMString`](domstring) reflecting the `aria-colindextext` attribute, which defines a human readable text alternative of aria-colindex.

[`Element.ariaColSpan`](element/ariacolspan)  
Is a [`DOMString`](domstring) reflecting the `aria-colspan` attribute, which defines the number of columns spanned by a cell or gridcell within a table, grid, or treegrid.

[`Element.ariaCurrent`](element/ariacurrent)  
Is a [`DOMString`](domstring) reflecting the `aria-current` attribute, which indicates the element that represents the current item within a container or set of related elements.

[`Element.ariaDescription`](element/ariadescription)  
Is a [`DOMString`](domstring) reflecting the `aria-description` attribute, which defines a string value that describes or annotates the current element.

[`Element.ariaDisabled`](element/ariadisabled)  
Is a [`DOMString`](domstring) reflecting the `aria-disabled` attribute, which indicates that the element is perceivable but disabled, so it is not editable or otherwise operable.

[`Element.ariaExpanded`](element/ariaexpanded)  
Is a [`DOMString`](domstring) reflecting the `aria-expanded` attribute, which indicates whether a grouping element owned or controlled by this element is expanded or collapsed.

[`Element.ariaHasPopup`](element/ariahaspopup)  
Is a [`DOMString`](domstring) reflecting the `aria-haspopup` attribute, which indicates the availability and type of interactive popup element, such as menu or dialog, that can be triggered by an element.

[`Element.ariaHidden`](element/ariahidden)  
Is a [`DOMString`](domstring) reflecting the `aria-hidden` attribute, which indicates whether the element is exposed to an accessibility API.

[`Element.ariaKeyShortcuts`](element/ariakeyshortcuts)  
Is a [`DOMString`](domstring) reflecting the `aria-keyshortcuts` attribute, which indicates keyboard shortcuts that an author has implemented to activate or give focus to an element.

[`Element.ariaLabel`](element/arialabel)  
Is a [`DOMString`](domstring) reflecting the `aria-label` attribute, which defines a string value that labels the current element.

[`Element.ariaLevel`](element/arialevel)  
Is a [`DOMString`](domstring) reflecting the `aria-level` attribute, which defines the hierarchical level of an element within a structure.

[`Element.ariaLive`](element/arialive)  
Is a [`DOMString`](domstring) reflecting the `aria-live` attribute, which indicates that an element will be updated, and describes the types of updates the user agents, assistive technologies, and user can expect from the live region.

[`Element.ariaModal`](element/ariamodal)  
Is a [`DOMString`](domstring) reflecting the `aria-modal` attribute, which indicates whether an element is modal when displayed.

[`Element.ariaMultiline`](element/ariamultiline)  
Is a [`DOMString`](domstring) reflecting the `aria-multiline` attribute, which indicates whether a text box accepts multiple lines of input or only a single line.

[`Element.ariaMultiSelectable`](element/ariamultiselectable)  
Is a [`DOMString`](domstring) reflecting the `aria-multiselectable` attribute, which indicates that the user may select more than one item from the current selectable descendants.

[`Element.ariaOrientation`](element/ariaorientation)  
Is a [`DOMString`](domstring) reflecting the `aria-orientation` attribute, which indicates whether the element's orientation is horizontal, vertical, or unknown/ambiguous.

[`Element.ariaPlaceholder`](element/ariaplaceholder)  
Is a [`DOMString`](domstring) reflecting the `aria-placeholder` attribute, which defines a short hint intended to aid the user with data entry when the control has no value.

[`Element.ariaPosInSet`](element/ariaposinset)  
Is a [`DOMString`](domstring) reflecting the `aria-posinset` attribute, which defines an element's number or position in the current set of listitems or treeitems.

[`Element.ariaPressed`](element/ariapressed)  
Is a [`DOMString`](domstring) reflecting the `aria-pressed` attribute, which indicates the current "pressed" state of toggle buttons.

[`Element.ariaReadOnly`](element/ariareadonly)  
Is a [`DOMString`](domstring) reflecting the `aria-readonly` attribute, which indicates that the element is not editable, but is otherwise operable.

[`Element.ariaRelevant`](element/ariarelevant)  
Is a [`DOMString`](domstring) reflecting the `aria-relevant` attribute, which indicates what notifications the user agent will trigger when the accessibility tree within a live region is modified. This is used to describe what changes in an `aria-live` region are relevant and should be announced.

[`Element.ariaRequired`](element/ariarequired)  
Is a [`DOMString`](domstring) reflecting the `aria-required` attribute, which indicates that user input is required on the element before a form may be submitted.

[`Element.ariaRoleDescription`](element/ariaroledescription)  
Is a [`DOMString`](domstring) reflecting the `aria-roledescription` attribute, which defines a human-readable, author-localized description for the role of an element.

[`Element.ariaRowCount`](element/ariarowcount)  
Is a [`DOMString`](domstring) reflecting the `aria-rowcount` attribute, which defines the total number of rows in a table, grid, or treegrid.

[`Element.ariaRowIndex`](element/ariarowindex)  
Is a [`DOMString`](domstring) reflecting the `aria-rowindex` attribute, which defines an element's row index or position with respect to the total number of rows within a table, grid, or treegrid.

[`Element.ariaRowIndexText`](element/ariarowindextext)  
Is a [`DOMString`](domstring) reflecting the `aria-rowindextext` attribute, which defines a human readable text alternative of aria-rowindex.

[`Element.ariaRowSpan`](element/ariarowspan)  
Is a [`DOMString`](domstring) reflecting the `aria-rowspan` attribute, which defines the number of rows spanned by a cell or gridcell within a table, grid, or treegrid.

[`Element.ariaSelected`](element/ariaselected)  
Is a [`DOMString`](domstring) reflecting the `aria-selected` attribute, which indicates the current "selected" state of elements that have a selected state.

[`Element.ariaSetSize`](element/ariasetsize)  
Is a [`DOMString`](domstring) reflecting the `aria-setsize` attribute, which defines the number of items in the current set of listitems or treeitems.

[`Element.ariaSort`](element/ariasort)  
Is a [`DOMString`](domstring) reflecting the `aria-sort` attribute, which indicates if items in a table or grid are sorted in ascending or descending order.

[`Element.ariaValueMax`](element/ariavaluemax)  
Is a [`DOMString`](domstring) reflecting the `aria-valueMax` attribute, which defines the maximum allowed value for a range widget.

[`Element.ariaValueMin`](element/ariavaluemin)  
Is a [`DOMString`](domstring) reflecting the `aria-valueMin` attribute, which defines the minimum allowed value for a range widget.

[`Element.ariaValueNow`](element/ariavaluenow)  
Is a [`DOMString`](domstring) reflecting the `aria-valueNow` attribute, which defines the current value for a range widget.

[`Element.ariaValueText`](element/ariavaluetext)  
Is a [`DOMString`](domstring) reflecting the `aria-valuetext` attribute, which defines the human readable text alternative of aria-valuenow for a range widget.

### Event handlers

[`Element.onfullscreenchange`](element/onfullscreenchange)  
An event handler for the `fullscreenchange` event, which is sent when the element enters or exits full-screen mode. This can be used to watch both for successful expected transitions, but also to watch for unexpected changes, such as when your app is running in the background.

[`Element.onfullscreenerror`](element/onfullscreenerror)  
An event handler for the `fullscreenerror` event, which is sent when an error occurs while attempting to change into full-screen mode.

## Methods

_`Element` inherits methods from its parents [`Node`](node), and its own parent, [`EventTarget`](eventtarget)._

[`EventTarget.addEventListener()`](eventtarget/addeventlistener)  
Registers an event handler to a specific event type on the element.

[`Element.attachShadow()`](element/attachshadow)  
Attaches a shadow DOM tree to the specified element and returns a reference to its [`ShadowRoot`](shadowroot).

[`Element.animate()`](element/animate) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
A shortcut method to create and run an animation on an element. Returns the created Animation object instance.

[`Element.append()`](element/append)  
Inserts a set of [`Node`](node) objects or [`DOMString`](domstring) objects after the last child of the element.

[`Element.closest()`](element/closest)  
Returns the [`Element`](element) which is the closest ancestor of the current element (or the current element itself) which matches the selectors given in parameter.

[`Element.createShadowRoot()`](element/createshadowroot) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Creates a [shadow DOM](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_shadow_DOM) on the element, turning it into a shadow host. Returns a [`ShadowRoot`](shadowroot).

[`Element.computedStyleMap()`](element/computedstylemap) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns a [`StylePropertyMapReadOnly`](stylepropertymapreadonly) interface which provides a read-only representation of a CSS declaration block that is an alternative to [`CSSStyleDeclaration`](cssstyledeclaration).

[`EventTarget.dispatchEvent()`](eventtarget/dispatchevent)  
Dispatches an event to this node in the DOM and returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that indicates whether no handler canceled the event.

[`Element.getAnimations()`](element/getanimations) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Returns an array of Animation objects currently active on the element.

[`Element.getAttribute()`](element/getattribute)  
Retrieves the value of the named attribute from the current node and returns it as an [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object).

[`Element.getAttributeNames()`](element/getattributenames)  
Returns an array of attribute names from the current element.

[`Element.getAttributeNS()`](element/getattributens)  
Retrieves the value of the attribute with the specified name and namespace, from the current node and returns it as an [`Object`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object).

[`Element.getBoundingClientRect()`](element/getboundingclientrect)  
Returns the size of an element and its position relative to the viewport.

[`Element.getClientRects()`](element/getclientrects)  
Returns a collection of rectangles that indicate the bounding rectangles for each line of text in a client.

[`Element.getElementsByClassName()`](element/getelementsbyclassname)  
Returns a live [`HTMLCollection`](htmlcollection) that contains all descendants of the current element that possess the list of classes given in the parameter.

[`Element.getElementsByTagName()`](element/getelementsbytagname)  
Returns a live [`HTMLCollection`](htmlcollection) containing all descendant elements, of a particular tag name, from the current element.

[`Element.getElementsByTagNameNS()`](element/getelementsbytagnamens)  
Returns a live [`HTMLCollection`](htmlcollection) containing all descendant elements, of a particular tag name and namespace, from the current element.

[`Element.hasAttribute()`](element/hasattribute)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element has the specified attribute or not.

[`Element.hasAttributeNS()`](element/hasattributens)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element has the specified attribute, in the specified namespace, or not.

[`Element.hasAttributes()`](element/hasattributes)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating if the element has one or more HTML attributes present.

[`Element.hasPointerCapture()`](element/haspointercapture)  
Indicates whether the element on which it is invoked has pointer capture for the pointer identified by the given pointer ID.

[`Element.insertAdjacentElement()`](element/insertadjacentelement)  
Inserts a given element node at a given position relative to the element it is invoked upon.

[`Element.insertAdjacentHTML()`](element/insertadjacenthtml)  
Parses the text as HTML or XML and inserts the resulting nodes into the tree in the position given.

[`Element.insertAdjacentText()`](element/insertadjacenttext)  
Inserts a given text node at a given position relative to the element it is invoked upon.

[`Element.matches()`](element/matches)  
Returns a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) indicating whether or not the element would be selected by the specified selector string.

[`Element.prepend()`](element/prepend)  
Inserts a set of [`Node`](node) objects or [`DOMString`](domstring) objects before the first child of the element.

[`Element.querySelector()`](element/queryselector)  
Returns the first [`Node`](node) which matches the specified selector string relative to the element.

[`Element.querySelectorAll()`](element/queryselectorall)  
Returns a [`NodeList`](nodelist) of nodes which match the specified selector string relative to the element.

[`Element.releasePointerCapture()`](element/releasepointercapture)  
Releases (stops) pointer capture that was previously set for a specific [`pointer event`](pointerevent).

[`ChildNode.remove()`](childnode/remove) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Removes the element from the children list of its parent.

[`Element.removeAttribute()`](element/removeattribute)  
Removes the named attribute from the current node.

[`Element.removeAttributeNS()`](element/removeattributens)  
Removes the attribute with the specified name and namespace, from the current node.

[`EventTarget.removeEventListener()`](eventtarget/removeeventlistener)  
Removes an event listener from the element.

[`Element.replaceChildren()`](element/replacechildren)  
Replaces the existing children of a [`Node`](node) with a specified new set of children.

[`Element.requestFullscreen()`](element/requestfullscreen) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Asynchronously asks the browser to make the element full-screen.

[`Element.requestPointerLock()`](element/requestpointerlock) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Allows to asynchronously ask for the pointer to be locked on the given element.

[`Element.scroll()`](element/scroll)  
Scrolls to a particular set of coordinates inside a given element.

[`Element.scrollBy()`](element/scrollby)  
Scrolls an element by the given amount.

[`Element.scrollIntoView()`](element/scrollintoview) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Scrolls the page until the element gets into the view.

[`Element.scrollTo()`](element/scrollto)  
Scrolls to a particular set of coordinates inside a given element.

[`Element.setAttribute()`](element/setattribute)  
Sets the value of a named attribute of the current node.

[`Element.setAttributeNS()`](element/setattributens)  
Sets the value of the attribute with the specified name and namespace, from the current node.

[`Element.setCapture()`](element/setcapture) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sets up mouse event capture, redirecting all mouse events to this element.

[`Element.setPointerCapture()`](element/setpointercapture)  
Designates a specific element as the capture target of future [pointer events](pointer_events).

[`Element.toggleAttribute()`](element/toggleattribute)  
Toggles a boolean attribute, removing it if it is present and adding it if it is not present, on the specified element.

### Obsolete methods

[`Element.getAttributeNode()`](element/getattributenode) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Retrieves the node representation of the named attribute from the current node and returns it as an [`Attr`](attr).

[`Element.getAttributeNodeNS()`](element/getattributenodens) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Retrieves the node representation of the attribute with the specified name and namespace, from the current node and returns it as an [`Attr`](attr).

[`Element.removeAttributeNode()`](element/removeattributenode) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Removes the node representation of the named attribute from the current node.

[`Element.setAttributeNode()`](element/setattributenode) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sets the node representation of the named attribute from the current node.

[`Element.setAttributeNodeNS()`](element/setattributenodens) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Sets the node representation of the attribute with the specified name and namespace, from the current node.

## Events

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`cancel`](htmldialogelement/cancel_event)  
Fires on a [`<dialog>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dialog) when the user instructs the browser that they wish to dismiss the current open dialog. For example, the browser might fire this event when the user presses the Esc key or clicks a "Close dialog" button which is part of the browser's UI.  
Also available via the [`oncancel`](globaleventhandlers/oncancel) property.

[`error`](element/error_event)  
Fired when a resource failed to load, or can't be used. For example, if a script has an execution error or an image can't be found or is invalid.  
Also available via the [`onerror`](globaleventhandlers/onerror) property.

[`scroll`](element/scroll_event)  
Fired when the document view or an element has been scrolled.  
Also available via the [`onscroll`](globaleventhandlers/onscroll) property.

[`select`](element/select_event)  
Fired when some text has been selected.  
Also available via the [`onselect`](globaleventhandlers/onselect) property.

[`show`](element/show_event)  
Fired when a [`contextmenu`](element/contextmenu_event) event was fired on/bubbled to an element that has a `contextmenu` attribute. <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Also available via the <span class="page-not-created">`onshow`</span> property.

[`wheel`](element/wheel_event)  
Fired when the user rotates a wheel button on a pointing device (typically a mouse).  
Also available via the [`onwheel`](globaleventhandlers/onwheel) property.

### Clipboard events

[`copy`](element/copy_event)  
Fired when the user initiates a copy action through the browser's user interface.  
Also available via the [`oncopy`](htmlelement/oncopy) property.

[`cut`](element/cut_event)  
Fired when the user initiates a cut action through the browser's user interface.  
Also available via the [`oncut`](htmlelement/oncut) property.

[`paste`](element/paste_event)  
Fired when the user initiates a paste action through the browser's user interface.  
Also available via the [`onpaste`](htmlelement/onpaste) property.

### Composition events

[`compositionend`](element/compositionend_event)  
Fired when a text composition system such as an [input method editor](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor) completes or cancels the current composition session.

[`compositionstart`](element/compositionstart_event)  
Fired when a text composition system such as an [input method editor](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor) starts a new composition session.

[`compositionupdate`](element/compositionupdate_event)  
Fired when a new character is received in the context of a text composition session controlled by a text composition system such as an [input method editor](https://developer.mozilla.org/en-US/docs/Glossary/Input_method_editor).

### Focus events

[`blur`](element/blur_event)  
Fired when an element has lost focus.  
Also available via the [`onblur`](globaleventhandlers/onblur) property.

[`focus`](element/focus_event)  
Fired when an element has gained focus.  
Also available via the [`onfocus`](globaleventhandlers/onfocus) property

[`focusin`](element/focusin_event)  
Fired when an element is about to gain focus.

[`focusout`](element/focusout_event)  
Fired when an element is about to lose focus.

### Fullscreen events

[`fullscreenchange`](element/fullscreenchange_event)  
Sent to an [`Element`](element) when it transitions into or out of [full-screen](fullscreen_api/guide) mode.  
Also available via the [`onfullscreenchange`](element/onfullscreenchange) property.

[`fullscreenerror`](element/fullscreenerror_event)  
Sent to an `Element` if an error occurs while attempting to switch it into or out of [full-screen](fullscreen_api/guide) mode.  
Also available via the [`onfullscreenerror`](element/onfullscreenerror) property.

### Keyboard events

`keydown`  
Fired when a key is pressed.  
Also available via the [`onkeydown`](globaleventhandlers/onkeydown) property.

`keypress`  
Fired when a key that produces a character value is pressed down. <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Also available via the [`onkeypress`](globaleventhandlers/onkeypress) property.

`keyup`  
Fired when a key is released.  
Also available via the [`onkeyup`](globaleventhandlers/onkeyup) property.

### Mouse events

[`auxclick`](element/auxclick_event)  
Fired when a non-primary pointing device button (e.g., any mouse button other than the left button) has been pressed and released on an element.  
Also available via the [`onauxclick`](globaleventhandlers/onauxclick) property.

[`click`](element/click_event)  
Fired when a pointing device button (e.g., a mouse's primary button) is pressed and released on a single element.  
Also available via the [`onclick`](globaleventhandlers/onclick) property.

[`contextmenu`](element/contextmenu_event)  
Fired when the user attempts to open a context menu.  
Also available via the [`oncontextmenu`](globaleventhandlers/oncontextmenu) property.

[`dblclick`](element/dblclick_event)  
Fired when a pointing device button (e.g., a mouse's primary button) is clicked twice on a single element.  
Also available via the [`ondblclick`](globaleventhandlers/ondblclick) property.

[`DOMActivate`](element/domactivate_event) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Occurs when an element is activated, for instance, through a mouse click or a keypress.

[`mousedown`](element/mousedown_event)  
Fired when a pointing device button is pressed on an element.  
Also available via the [`onmousedown`](globaleventhandlers/onmousedown) property.

[`mouseenter`](element/mouseenter_event)  
Fired when a pointing device (usually a mouse) is moved over the element that has the listener attached.  
Also available via the [`onmouseenter`](globaleventhandlers/onmouseenter) property.

[`mouseleave`](element/mouseleave_event)  
Fired when the pointer of a pointing device (usually a mouse) is moved out of an element that has the listener attached to it.  
Also available via the [`onmouseleave`](globaleventhandlers/onmouseleave) property.

[`mousemove`](element/mousemove_event)  
Fired when a pointing device (usually a mouse) is moved while over an element.  
Also available via the [`onmousemove`](globaleventhandlers/onmousemove) property.

[`mouseout`](element/mouseout_event)  
Fired when a pointing device (usually a mouse) is moved off the element to which the listener is attached or off one of its children.  
Also available via the [`onmouseout`](globaleventhandlers/onmouseout) property.

[`mouseover`](element/mouseover_event)  
Fired when a pointing device is moved onto the element to which the listener is attached or onto one of its children.  
Also available via the [`onmouseover`](globaleventhandlers/onmouseover) property.

[`mouseup`](element/mouseup_event)  
Fired when a pointing device button is released on an element.  
Also available via the [`onmouseup`](globaleventhandlers/onmouseup) property.

[`webkitmouseforcechanged`](element/webkitmouseforcechanged_event)  
Fired each time the amount of pressure changes on the trackpadtouchscreen.

[`webkitmouseforcedown`](element/webkitmouseforcedown_event)  
Fired after the mousedown event as soon as sufficient pressure has been applied to qualify as a "force click".

[`webkitmouseforcewillbegin`](element/webkitmouseforcewillbegin_event)  
Fired before the [`mousedown`](element/mousedown_event) event.

[`webkitmouseforceup`](element/webkitmouseforceup_event)  
Fired after the [`webkitmouseforcedown`](element/webkitmouseforcedown_event) event as soon as the pressure has been reduced sufficiently to end the "force click".

### Touch events

[`touchcancel`](element/touchcancel_event)  
Fired when one or more touch points have been disrupted in an implementation-specific manner (for example, too many touch points are created).  
Also available via the [`ontouchcancel`](globaleventhandlers/ontouchcancel) property.

[`touchend`](element/touchend_event)  
Fired when one or more touch points are removed from the touch surface.  
Also available via the [`ontouchend`](globaleventhandlers/ontouchend) property

[`touchmove`](element/touchmove_event)  
Fired when one or more touch points are moved along the touch surface.  
Also available via the [`ontouchmove`](globaleventhandlers/ontouchmove) property

[`touchstart`](element/touchstart_event)  
Fired when one or more touch points are placed on the touch surface.  
Also available via the [`ontouchstart`](globaleventhandlers/ontouchstart) property

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/web-animations-1/">Web Animations</a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the <code>getAnimations()</code> method.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents2/#extensions-to-the-element-interface">Pointer Events – Level 2<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added the following event handlers: <code>ongotpointercapture</code> and <code>onlostpointercapture</code>.<br />
Added the following methods: <code>setPointerCapture()</code> and <code>releasePointerCapture()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents1/#extensions-to-the-element-interface">Pointer Events<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the following event handlers: <code>ongotpointercapture</code> and <code>onlostpointercapture</code>.<br />
Added the following methods: <code>setPointerCapture()</code> and <code>releasePointerCapture()</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/selectors-api/#interface-definitions">Selectors API Level 1<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the following methods: <code>querySelector()</code> and <code>querySelectorAll()</code>.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/pointerlock/#extensions-to-the-element-interface">Pointer Lock<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added the <code>requestPointerLock()</code> method.</td></tr><tr class="even"><td><a href="https://fullscreen.spec.whatwg.org/#api">Fullscreen API<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the <code>requestFullscreen()</code> method.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/DOM-Parsing/#extensions-to-the-element-interface">DOM Parsing and Serialization<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the following properties: <code>innerHTML</code>, and <code>outerHTML</code>.<br />
Added the following method: <code>insertAdjacentHTML()</code>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/cssom-view/#extension-to-the-element-interface">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added the following properties: <code>scrollTop</code>, <code>scrollLeft</code>, <code>scrollWidth</code>, <code>scrollHeight</code>, <code>clientTop</code>, <code>clientLeft</code>, <code>clientWidth</code>, and <code>clientHeight</code>.<br />
Added the following methods: <code>getClientRects()</code>, <code>getBoundingClientRect()</code>, <code>scroll()</code>, <code>scrollBy()</code>, <code>scrollTo()</code> and <code>scrollIntoView()</code>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/ElementTraversal/#ecmascript-bindings">Element Traversal Specification<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added inheritance of the <a href="elementtraversal"><code>ElementTraversal</code></a> interface.</td></tr><tr class="even"><td><a href="https://dom.spec.whatwg.org/#interface-element">DOM<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added the following methods: <code>closest()</code>, <code>insertAdjacentElement()</code> and <code>insertAdjacentText()</code>.<br />
Moved <code>hasAttributes()</code> from the <code>Node</code> interface to this one.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/dom/#interface-element">DOM4<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Removed the following methods: <code>setIdAttribute()</code>, <code>setIdAttributeNS()</code>, and <code>setIdAttributeNode()</code>.<br />
Modified the return value of <code>getElementsByTagName()</code> and <code>getElementsByTagNameNS()</code>.<br />
Removed the <code>schemaTypeInfo</code> property.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-3-Core/core.html#ID-745549614">Document Object Model (DOM) Level 3 Core Specification<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Added the following methods: <code>setIdAttribute()</code>, <code>setIdAttributeNS()</code>, and <code>setIdAttributeNode()</code>. These methods were never implemented and have been removed in later specifications.<br />
Added the <code>schemaTypeInfo</code> property. This property was never implemented and has been removed in later specifications.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Core/core.html#ID-745549614">Document Object Model (DOM) Level 2 Core Specification<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>The <code>normalize()</code> method has been moved to <a href="node"><code>Node</code></a>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-core.html#ID-745549614">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'Element' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Element`

1

12

1

4

8

1

1

18

4

10.1

1

1.0

`DOMActivate_event`

Yes

79

Yes

No

No

Yes

?

Yes

Yes

No

?

Yes

`DOMMouseScroll_event`

No

No

1

No

No

No

No

No

4

No

No

No

`MozMousePixelScroll_event`

No

≤18-79

Yes

No

No

No

No

No

Yes

No

No

No

`MSGestureChange_event`

No

12-79

No

10

No

No

No

No

No

No

No

No

`MSGestureEnd_event`

No

12-79

No

10

No

No

No

No

No

No

No

No

`MSGestureHold_event`

No

12-79

No

10

No

No

No

No

No

No

No

No

`MSGestureStart_event`

No

12-79

No

10

No

No

No

No

No

No

No

No

`MSGestureTap_event`

No

12-79

No

10

No

No

No

No

No

No

No

No

`MSInertiaStart_event`

No

12-79

No

10

No

No

No

No

No

No

No

No

`MSManipulationStateChanged_event`

No

12-79

No

Yes

No

No

No

No

No

No

No

No

`afterscriptexecute_event`

No

No

2

?

No

No

No

No

4

No

No

No

`animate`

36

79

48

No

23

13.1

Yes

37

36

48

24

13.4

3.0

`assignedSlot`

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

`attachShadow`

53

79

63

No

40

10

53

53

63

41

10

6.0

`attributes`

1

12

1

5.5

8

1

1

18

4

10.1

1

1.0

`attributeStyleMap`

66

79

No

No

53

No

66

66

No

47

No

9.0

`auxclick_event`

55

≤79

53

Starting in Firefox 68, the `auxclick` event is used to trigger the _new tab on middle-click_ action; previously, this had been done with the `click` event. Apps can prevent middle-click from opening new tabs (or middle-click to paste, if that feature is enabled) by intercepting `auxclick` on links, and `auxclick` event handlers can now open popups without triggering the popup blocker.

No

42

No

55

55

53

42

No

6.0

`beforescriptexecute_event`

No

No

2

?

No

No

No

No

4

No

No

No

`blur_event`

1

12

24

6-24

The interface for this event is [`Event`](https://developer.mozilla.org/docs/Web/API/Event), not [`FocusEvent`](https://developer.mozilla.org/docs/Web/API/FocusEvent).

9

11.6

3.1

1

18

24

6-24

The interface for this event is [`Event`](https://developer.mozilla.org/docs/Web/API/Event), not [`FocusEvent`](https://developer.mozilla.org/docs/Web/API/FocusEvent).

12.1

2

1.0

`classList`

22

8-22

Not supported for SVG elements.

16

12-16

Not supported for SVG elements.

3.6

10

Not supported for SVG elements.

11.5

6.1

6-6.1

Not supported for SVG elements.

4.4

3-4.4

Not supported for SVG elements.

25

18-25

Not supported for SVG elements.

4

11.5

7

5-7

Not supported for SVG elements.

1.5

1.0-1.5

Not supported for SVG elements.

`className`

22

1-22

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

12

1

5

8

1

≤37

1-≤37

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

25

18-25

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

4

10.1

1

1.5

1.0-1.5

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

`click_event`

1

12

6

Beginning in Firefox 68, Firefox no longer incorrectly sends a `click` event for buttons other than the primary mouse button; previouly, there were circumstances in which this would occur. One example: middle-clicking a link would send a `click` to the document's `<html>` element.

9

11.6

3

1

18

6

12.1

1

1.0

`clientHeight`

1

12

1

5

8

3

1

18

4

10.1

1

1.0

`clientLeft`

1

12

1

5

8

3

1

18

4

10.1

1

1.0

`clientTop`

1

12

1

5

8

3

1

18

4

10.1

1

1.0

`clientWidth`

1

12

1

5

8

3

1

18

4

10.1

1

1.0

`closest`

41

15

35

No

28

6

41

41

35

28

9

4.0

`compositionend_event`

Yes

12

9

Yes

Yes

Yes

Yes

Yes

Yes

?

?

Yes

`compositionstart_event`

Yes

12

9

Yes

Yes

Yes

Yes

Yes

Yes

?

?

Yes

`compositionupdate_event`

Yes

12

9

Yes

Yes

Yes

Yes

Yes

Yes

?

?

Yes

`computedStyleMap`

66

79

No

No

53

No

66

66

No

47

No

9.0

`contextmenu_event`

1

12

6

9

10.5

3

1

18

6

11.1

1

1.0

`copy_event`

1

≤18

Yes

Yes

15

Yes

1

18

Yes

14

Yes

1.0

`createShadowRoot`

35

In Chrome 45, the ability to have multiple shadow roots was deprecated.

25-36

79

59-61

29-59

No

22

In Opera 32, the ability to have multiple shadow roots was deprecated.

15-23

No

37

In version 45, the ability to have multiple shadow roots was deprecated.

4.4-37

35

In Chrome 45, the ability to have multiple shadow roots was deprecated.

25-36

59-61

29-59

22

In Opera 32, the ability to have multiple shadow roots was deprecated.

14-24

No

3.0

In Samsung Internet 5.0, the ability to have multiple shadow roots was deprecated.

1.5-3.0

`currentStyle`

No

No

No

5

≤12.1-15

No

No

No

No

≤12.1-14

No

No

`cut_event`

1

≤18

Yes

Yes

15

Yes

1

18

Yes

14

Yes

1.0

`dblclick_event`

1

12

6

Starting in Firefox 68, `dblclick` events are only sent for the primary mouse button, per the specification.

11

11.6

3

No

No

6

12.1

1

No

`error_event`

Yes

≤79

Yes

?

?

?

Yes

Yes

Yes

?

?

Yes

`focus_event`

1

12

24

6-24

The interface for this event is [`Event`](https://developer.mozilla.org/docs/Web/API/Event), not [`FocusEvent`](https://developer.mozilla.org/docs/Web/API/FocusEvent).

9

11.6

3.1

1

18

24

6-24

The interface for this event is [`Event`](https://developer.mozilla.org/docs/Web/API/Event), not [`FocusEvent`](https://developer.mozilla.org/docs/Web/API/FocusEvent).

12.1

2

1.0

`focusin_event`

1

12

52

9

11.6

5

1

18

52

12.1

4.2

1.0

`focusout_event`

1

12

52

9

11.6

5

1

18

52

12.1

4.2

1.0

`fullscreenchange_event`

71

57

≤79

64

10

?

44

?

71

57

71

57

64

10

43

?

7.0

`fullscreenerror_event`

71

57

≤79

64

10

?

44

?

71

57

71

57

64

10

43

?

7.0

`gesturechange_event`

No

No

No

No

No

9.1

No

No

No

No

2

No

`gestureend_event`

No

No

No

No

No

9.1

No

No

No

No

2

No

`gesturestart_event`

No

No

No

No

No

9.1

No

No

No

No

2

No

`getAnimations`

84

79

67-79

Does not support the `subtree` option.

44-67

Does not automatically flush pending style changes and does not support the `subtree` option.

38-44

Does not automatically flush pending style changes and does not support the `subtree` option.

84

79

75

63-75

No

70

66

54-66

Does not support the `subtree` option.

31-54

Does not automatically flush pending style changes and does not support the `subtree` option.

25-31

Does not automatically flush pending style changes and does not support the `subtree` option.

Yes

Does not support the `subtree` option.

84

84

79

67-79

Does not support the `subtree` option.

44-67

Does not automatically flush pending style changes and does not support the `subtree` option.

38-44

Does not automatically flush pending style changes and does not support the `subtree` option.

79

63-79

60

57

48-57

Does not support the `subtree` option.

32-48

Does not automatically flush pending style changes and does not support the `subtree` option.

25-32

Does not automatically flush pending style changes and does not support the `subtree` option.

Yes

Does not support the `subtree` option.

14.0

`getAttribute`

1

12

1

5

8

1

1

18

4

10.1

1

1.0

`getAttributeNames`

61

18

45

No

48

10.1

61

61

45

45

10.3

8.0

`getAttributeNode`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

`getAttributeNodeNS`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`getAttributeNS`

1

12

1

Starting in Firefox 13, `null` is always returned instead of the empty string, as per the DOM4 specification. Previously, there were cases in which an empty string could be returned.

9

≤12.1

1

1

18

4

Starting in Firefox 13, `null` is always returned instead of the empty string, as per the DOM4 specification. Previously, there were cases in which an empty string could be returned.

≤12.1

1

1.0

`getBoundingClientRect`

2

12

3

4

9.5

4

2

18

4

10.1

3.2

Safari for iOS will modify the effective viewport based on the user zoom. This results in incorrect values whenever the user has zoomed.

1.0

`getClientRects`

2

12

3

5

9.5

4

2

18

4

10.1

3.2

1.0

`getElementsByClassName`

1

16

12-16

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

3

Prior to Firefox 19, this method was returning a `NodeList`; it was then changed to reflect the change in the spec.

9

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

9.5

6

1

18

4

10.1

6

1.0

`getElementsByTagName`

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

12

1

Prior to Firefox 19, this method was returning a `NodeList`; it was then changed to reflect the change in the spec.

5.5

8

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

18

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

4

Prior to Firefox 19, this method was returning a `NodeList`; it was then changed to reflect the change in the spec.

10.1

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1.0

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

`getElementsByTagNameNS`

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

12

1

\["The behavior of `element.getElementsByTagNameNS` changed between Firefox 3.5 and Firefox 3.6. In Firefox 3.5 and before, this function would automatically case-fold any queries so that a search for \\"foo\\" would match \\"Foo\\" or \\"foo\\". In Firefox 3.6 and later this function is now case-sensitive so that a query for \\"foo\\" will only match \\"foo\\" and not \\"Foo\\". For more background on this, please see the [comment from Henri Sivonen about the change](https://bugzil.la/542185#c5). You can also look at the [relevant part of the standard, which states which parts of the API are case-sensitive and which parts aren't.](https://developer.mozilla.org/docs/Case_Sensitivity_in_class_and_id_Names)", "Prior to Firefox 19, this method was returning a `NodeList`; it was then changed to reflects the spec change."\]

9

≤12.1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

18

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

4

Prior to Firefox 19, this method was returning a `NodeList`; it was then changed to reflects the spec change.

≤12.1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

1.0

Initially, this method was returning a `NodeList`; it was then changed to reflect the spec change.

`hasAttribute`

1

12

1

8

8

1

1

18

4

10.1

1

1.0

`hasAttributeNS`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`hasAttributes`

1

12

1

Before Firefox 35, it was implemented on the `Node` interface.

8

≤12.1

1

1

18

4

Before Firefox 35, it was implemented on the `Node` interface.

≤12.1

1

1.0

`hasPointerCapture`

55

79

59

41

No

42

13

55

55

79

41

42

13

6.0

`id`

23

1-23

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

12

1

5

≤12.1

1

≤37

1-≤37

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

25

18-25

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

4

≤12.1

1

1.5

1.0-1.5

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

`innerHTML`

33

This API was previously available on the `Node` API.

12

1

4

8

9

This API was previously available on the `Node` API.

4.4

This API was previously available on the `Node` API.

33

This API was previously available on the `Node` API.

4

10.1

9

This API was previously available on the `Node` API.

2.0

This API was previously available on the `Node` API.

`insertAdjacentElement`

1

17

12-17

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

48

5

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

8

3

1

18

48

10.1

1

1.0

`insertAdjacentHTML`

1

17

12-17

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

8

4

\["Before Internet Explorer 10, throws an \\"Invalid target element for this operation.\\" error when called on a `<table>`, `<tbody>`, `<thead>`, or `<tr>` element.", "Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement)."\]

8

4

1

18

8

10.1

4

1.0

`insertAdjacentText`

1

17

12-17

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

48

5

Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).

≤12.1

4

2.3

18

48

≤12.1

4

1.0

`keydown_event`

Yes

≤18

Yes

?

?

?

Yes

Yes

Yes

?

?

Yes

`keypress_event`

Yes

Chrome does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

≤18

Yes

As of Firefox 65, the `keypress` event is no longer fired for [non-printable keys](<https://developer.mozilla.org/docs/Web/API/KeyboardEvent/keyCode#Non-printable_keys_(function_keys)>), except for the Enter key, and the Shift + Enter and Ctrl + Enter key combinations (these were kept for cross-browser compatibility purposes).

?

?

?

Yes

Chrome does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

Yes

Chrome does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

Yes

As of Firefox 65, the `keypress` event is no longer fired for [non-printable keys](<https://developer.mozilla.org/docs/Web/API/KeyboardEvent/keyCode#Non-printable_keys_(function_keys)>), except for the Enter key, and the Shift + Enter and Ctrl + Enter key combinations (these were kept for cross-browser compatibility purposes).

?

?

Yes

Samsung Internet does not fire the `keypress` event for [known keyboard shortcuts](https://crbug.com/13891#c50). Which keyboard shortcuts are known depends on the user's system. Use the `keydown` event to implement keyboard shortcuts.

`keyup_event`

Yes

≤18

Yes

?

?

?

Yes

Yes

Yes

?

?

Yes

`localName`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`matches`

33

4

15

12

12

34

44

3.6

\["Prior to Firefox 4, invalid selector strings caused false to be returned instead of throwing an exception.", "See [bug 1119718](https://bugzil.la/1119718) for removal."\]

9

21

15

11.5-15

7

5

4.4

≤37

33

18

34

44

4

See [bug 1119718](https://bugzil.la/1119718) for removal.

21

14

11.5-14

8

4.2

2.0

1.0

`mousedown_event`

2

12

6

9

11.6

4

1

18

6

12.1

3.2

1.0

`mouseenter_event`

30

12

10

5.5

17

6.1

≤37

30

10

18

6.1

2.0

`mouseleave_event`

30

12

10

5.5

17

6.1

≤37

30

10

18

6.1

2.0

`mousemove_event`

2

12

6

9

11.6

4

≤37

18

6

12.1

3.2

1.0

`mouseout_event`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`mouseover_event`

2

12

6

9

9.5

4

≤37

18

6

10.1

3.2

1.0

`mouseup_event`

2

12

6

9

11.6

4

≤37

18

6

12.1

3.2

1.0

`mousewheel_event`

31

≤79

No

?

?

?

?

?

No

?

?

?

`msContentZoom_event`

No

12-79

No

Yes

No

No

No

No

No

No

No

No

`namespaceURI`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`nextElementSibling`

1

12

3.5

9

10

4

≤37

18

4

10.1

3

1.0

`onfullscreenchange`

71

57

79

64

10

No

Yes

No

71

57

71

57

64

10

Yes

No

7.0

`onfullscreenerror`

71

57

79

64

10

No

Yes

No

71

57

71

57

64

10

Yes

No

7.0

`openOrClosedShadowRoot`

No

No

63

Available only to [WebExtensions](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions).

No

No

No

No

No

63

Available only to [WebExtensions](https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions).

No

No

No

`outerHTML`

33

This API was previously available on the `Node` API.

12

11

4

8

9

4.4

This API was previously available on the `Node` API.

33

This API was previously available on the `Node` API.

14

10.1

9

2.0

This API was previously available on the `Node` API.

`overflow_event`

No

No

Yes

No

No

No

No

No

Yes

No

No

No

`part`

73

79

72

71

No

60

13.1

73

73

79

52

13.4

11.0

`paste_event`

1

12

22

8

Before Internet Explorer 11, copying files does not trigger the `paste` event.

15

5

1

18

22

14

4.2

1.0

`prefix`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`previousElementSibling`

1

12

3.5

9

10

4

≤37

18

4

10.1

3

1.0

`releasePointerCapture`

55

12

59

41

11

10

42

13

55

55

79

41

42

13

6.0

`removeAttribute`

1

12

This function doesn't respect boolean attributes' default values. See [bug 12087679](https://developer.microsoft.com/microsoft-edge/platform/issues/12087679/).

1

5

8

1

1

18

4

10.1

1

1.0

`removeAttributeNode`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

`removeAttributeNS`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`requestFullscreen`

71

15

79

79

12-14

64

9

Before Firefox 44, Firefox incorrectly allowed elements inside a `<frame>` or `<object>` element to request, and to be granted, fullscreen. In Firefox 44 and onwards this has been fixed: only elements in the top-level document or in an `<iframe>` element with the `allowfullscreen` attribute can be displayed fullscreen.

11

58

15

12-15

6

71

≤37

71

18

64

9

Before Firefox 44, Firefox incorrectly allowed elements inside a `<frame>` or an `<object>` to request, and to be granted, fullscreen. In Firefox 44 and onwards this has been fixed: only elements in the top-level document or in an `<iframe>` with the `allowfullscreen` attribute can be displayed fullscreen.

50

14

12-14

6

Only available on iPad, not on iPhone. Shows an overlay button which can not be disabled.

10.0

1.0

`requestPointerLock`

37

Yes

13

79

50

Yes

No

24

Yes

10.1

Yes

37

Yes

37

Yes

Yes

24

Yes

No

3.0

Yes

`runtimeStyle`

No

No

No

5

No

No

No

No

No

No

No

No

`scroll`

61

79

36

No

48

10.1

61

61

36

45

10.3

8.0

`scroll_event`

Yes

≤18

Yes

?

?

?

Yes

Yes

Yes

?

?

Yes

`scrollBy`

61

79

36

No

48

10.1

61

61

36

45

10.3

8.0

`scrollHeight`

1

12

21

3-21

In Firefox versions prior to 21, when an element's content does not generate a vertical scrollbar, then its `scrollHeight` property is equal to its `clientHeight` property. This can mean either the content is too short to require a scrollbar or that the element has a CSS style `overflow` value of `visible` (non-scrollable).

5

In Internet Explorer 5 through 7, if padding is set, the value of `scrollHeight` is equal to the sum of the top and bottom padding. This behavior was fixed in Internet Explorer 8.

8

1

1

18

21

4-21

In Firefox versions prior to 21, when an element's content does not generate a vertical scrollbar, then its `scrollHeight` property is equal to its `clientHeight` property. This can mean either the content is too short to require a scrollbar or that the element has a CSS style `overflow` value of `visible` (non-scrollable).

10.1

1

1.0

`scrollIntoView`

1

79

17-79

The only parameter supported is `alignToTop`.

12-17

\["Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).", "No support for `smooth` behavior."\]

1

5

\["Only supported for [`HTMLElement`](https://developer.mozilla.org/docs/Web/API/HTMLElement), not all `Element` objects, such as [`SVGElement`](https://developer.mozilla.org/docs/Web/API/SVGElement).", "No support for `smooth` behavior or `center` options."\]

≤12.1

3

No support for `smooth` behavior or `center` options.

1

18

4

≤12.1

1

No support for `smooth` behavior or `center` options.

1.0

`scrollIntoViewIfNeeded`

1

79

No

No

15

3

1

18

No

14

1

1.0

`scrollLeft`

1

For right-to-left elements, this property uses 0-100 (most left to most right) instead of negative values. See [bug 721759](https://crbug.com/721759).

12

\["From Edge 79, for right-to-left elements, this property uses 0-100 (most left to most right) instead of negative values. See [bug 721759](https://crbug.com/721759).", "Before Edge 79, for right-to-left elements, this property uses 100-0 (most left to most right) instead of negative values."\]

1

5

For right-to-left elements, this property uses 100-0 (most left to most right) instead of negative values.

8

1

1

For right-to-left elements, this property uses 0-100 (most left to most right) instead of negative values. See [bug 721759](https://crbug.com/721759).

18

For right-to-left elements, this property uses 0-100 (most left to most right) instead of negative values. See [bug 721759](https://crbug.com/721759).

4

10.1

1

1.0

For right-to-left elements, this property uses 0-100 (most left to most right) instead of negative values. See [bug 721759](https://crbug.com/721759).

`scrollLeftMax`

No

No

16

No

No

No

No

No

16

No

No

No

`scrollTo`

61

79

36

No

48

10.1

61

61

36

45

10.3

8.0

`scrollTop`

1

12

1

5

8

1

1

18

4

10.1

1

1.0

`scrollTopMax`

No

No

16

No

No

No

No

No

16

No

No

No

`scrollWidth`

1

12

1

5

In Internet Explorer 5 through 7, if padding is set, the value of `scrollWidth` is equal to the sum of the left and right padding. This behavior was fixed in Internet Explorer 8.

≤12.1

1

1

18

4

≤12.1

1

1.0

`select_event`

Yes

≤18

Yes

?

?

?

Yes

Yes

Yes

?

?

Yes

`setAttribute`

1

12

1

5

In Internet Explorer 7 and earlier, `setAttribute` doesn't set styles and removes events when you try to set them.

8

1

1

18

4

10.1

1

1.0

`setAttributeNode`

1

12

1

6

≤12.1

1

1

18

4

≤12.1

1

1.0

`setAttributeNodeNS`

1

12

Returns a `ClientRectList` with [ClientRect](<http://msdn.microsoft.com/en-us/library/hh826029(VS.85).aspx>) objects (which do not contain `x` and `y` properties) instead of [`DOMRect`](https://developer.mozilla.org/docs/Web/API/DOMRect) objects.

1

9

Returns a `ClientRectList` with [ClientRect](<http://msdn.microsoft.com/en-us/library/hh826029(VS.85).aspx>) objects (which do not contain `x` and `y` properties) instead of [`DOMRect`](https://developer.mozilla.org/docs/Web/API/DOMRect) objects.

≤12.1

1

1

18

4

≤12.1

1

1.0

`setAttributeNS`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`setCapture`

No

12-79

4

5

The `retargetToElement` parameter to `Element.setCapture()` was introduced in Internet Explorer 5.5.

No

No

No

No

4

No

No

No

`setPointerCapture`

55

12

59

Before Firefox 82, `setPointerCapture()` throws `InvalidPointerId` for an invalid `pointerId` argument. From Firefox 82, it throws [the specified](https://w3c.github.io/pointerevents/#setting-pointer-capture) `NotFoundError` exception. See [bug 1662124](https://bugzil.la/1662124).

41

11

10

42

13

55

55

79

Before Firefox 82, `setPointerCapture()` throws `InvalidPointerId` for an invalid `pointerId` argument. From Firefox 82, it throws [the specified](https://w3c.github.io/pointerevents/#setting-pointer-capture) `NotFoundError` exception. See [bug 1662124](https://bugzil.la/1662124).

41

42

13

6.0

`shadowRoot`

35

79

63

No

22

10

37

35

63

22

10

3.0

`show_event`

No

No

Yes

?

?

?

No

No

Yes

?

?

No

`slot`

53

79

63

No

40

10

53

53

63

41

10

6.0

`tabStop`

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

`tagName`

1

12

1

5

8

1

1

18

4

10.1

1

1.0

`toggleAttribute`

69

18

63

No

56

12

69

69

63

48

Yes

10.0

`touchcancel_event`

22

12

52

No

No

No

≤37

25

6

Yes

Yes

1.5

`touchend_event`

22

12

52

No

No

No

≤37

25

6

Yes

Yes

1.5

`touchmove_event`

22

12

52

No

No

No

≤37

25

6

Yes

Yes

1.5

`touchstart_event`

22

12

52

No

No

No

≤37

25

6

Yes

Yes

1.5

`underflow_event`

No

No

Yes

No

No

No

No

No

Yes

No

No

No

`webkitmouseforcechanged_event`

No

No

No

No

No

Yes

No

No

No

No

Yes

No

`webkitmouseforcedown_event`

No

No

No

No

No

Yes

No

No

No

No

Yes

No

`webkitmouseforceup_event`

No

No

No

No

No

Yes

No

No

No

No

Yes

No

`webkitmouseforcewillbegin_event`

No

No

No

No

No

Yes

No

No

No

No

Yes

No

`wheel_event`

61

12

17

9

Internet Explorer only exposes the wheel event via `addEventListener`; there is no `onwheel` attribute on DOM objects. See [IE bug 782835](https://connect.microsoft.com/IE/feedback/details/782835/missing-onwheel-attribute-for-the-wheel-event-although-its-supported-via-addeventlistener).

48

7

61

61

17

45

7

8.0

`ariaAtomic`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaAutoComplete`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaBusy`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaChecked`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaColCount`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaColIndex`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaColSpan`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaCurrent`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaDescription`

83

83

No

No

69

No

83

83

No

59

No

13.0

`ariaDisabled`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaExpanded`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaHasPopup`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaHidden`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaKeyShortcuts`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaLabel`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaLevel`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaLive`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaModal`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaMultiLine`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaMultiSelectable`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaOrientation`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaPlaceholder`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaPosInSet`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaPressed`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaReadOnly`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaRelevant`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaRequired`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaRoleDescription`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaRowCount`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaRowIndex`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaRowSpan`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaSelected`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaSetSize`

84

84

No

No

70

12.1

84

84

No

60

12.2

14.0

`ariaSort`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaValueMax`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaValueMin`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaValueNow`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`ariaValueText`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

`append`

54

17

49

No

41

10

54

54

49

41

10

6.0

`childElementCount`

1

12

3.5

9

10

4

1

18

4

10.1

3

1.0

`children`

1

12

3.5

9

6-9

Also includes non-standard `HTMLCommentElement` nodes.

10

4

1

18

4

10.1

3

1.0

`firstElementChild`

1

12

3.5

9

10

4

1

18

4

10.1

3

1.0

`lastElementChild`

1

12

3.5

9

10

4

1

18

4

10.1

3

1.0

`prepend`

54

17

49

No

41

10

54

54

49

41

10

6.0

`querySelector`

1

12

3.5

9

8

`querySelector()` is supported, but only for CSS 2.1 selectors.

10

3.1

1

18

4

10.1

2

1.0

`querySelectorAll`

1

12

3.5

9

8

`querySelectorAll()` is supported, but only for CSS 2.1 selectors.

10

3.1

1

18

4

10.1

2

1.0

`replaceChildren`

86

86

78

No

72

14

86

86

79

61

14

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element</a>
