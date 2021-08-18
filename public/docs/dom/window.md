Window
======

The `Window` interface represents a window containing a [DOM](https://developer.mozilla.org/en-US/docs/Glossary/DOM) document; the `document` property points to the [DOM document](document) loaded in that window. A window for a given document can be obtained using the [`document.defaultView`](document/defaultview) property.

A global variable, `window`, representing the window in which the script is running, is exposed to JavaScript code.

The `Window` interface is home to a variety of functions, namespaces, objects, and constructors which are not necessarily directly associated with the concept of a user interface window. However, the `Window` interface is a suitable place to include these items that need to be globally available. Many of these are documented in the [JavaScript Reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference) and the [DOM Reference](document_object_model).

In a tabbed browser, each tab is represented by its own `Window` object; the global `window` seen by JavaScript code running within a given tab always represents the tab in which the code is running. That said, even in a tabbed browser, some properties and methods still apply to the overall window that contains the tab, such as [`resizeTo()`](window/resizeto) and [`innerHeight`](window/innerheight). Generally, anything that can't reasonably pertain to a tab pertains to the window instead.

Constructors
------------

See also the [DOM Interfaces](document_object_model).

[`DOMParser`](domparser)  
`DOMParser` can parse XML or HTML source stored in a string into a DOM [Document](document). `DOMParser` is specified in [DOM Parsing and Serialization](https://w3c.github.io/DOM-Parsing/).

[`HTMLImageElement.Image`](htmlimageelement/image)  
Used for creating an [`HTMLImageElement`](htmlimageelement).

[`HTMLOptionElement.Option`](htmloptionelement/option)  
Used for creating an [`HTMLOptionElement`](htmloptionelement).

 [`StaticRange`](staticrange) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>   
Returns a [`StaticRange()`](staticrange/staticrange) constructor which creates a [`StaticRange`](staticrange) object.

[`Worker`](worker)  
Used for creating a [Web worker.](web_workers_api/using_web_workers)

[`XMLSerializer`](xmlserializer)  
Converts a DOM tree into XML or HTML source.

Properties
----------

*This interface inherits properties from the [`EventTarget`](eventtarget) interface and implements properties from the [`WindowOrWorkerGlobalScope`](windoworworkerglobalscope) and [`WindowEventHandlers`](windoweventhandlers) mixins.*

Note that properties which are objects (e.g.,. for overriding the prototype of built-in elements) are listed in a separate section below.

 [`Window.closed`](window/closed) <span class="badge inline readonly">Read only </span>   
This property indicates whether the current window is closed or not.

 [`Window.console`](window/console) <span class="badge inline readonly">Read only </span>   
Returns a reference to the console object which provides access to the browser's debugging console.

 [`Window.controllers`](window/controllers) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the XUL controller objects for the current chrome window.

 [`Window.customElements`](window/customelements) <span class="badge inline readonly">Read only </span>   
Returns a reference to the [`CustomElementRegistry`](customelementregistry) object, which can be used to register new [custom elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements) and get information about previously registered custom elements.

 [`Window.crypto`](window/crypto) <span class="badge inline readonly">Read only </span>   
Returns the browser crypto object.

 [`Window.devicePixelRatio`](window/devicepixelratio) <span class="badge inline readonly">Read only </span>   
Returns the ratio between physical pixels and device independent pixels in the current display.

 [`Window.document`](window/document) <span class="badge inline readonly">Read only </span>   
Returns a reference to the document that the window contains.

 <span class="page-not-created">`Window.DOMMatrix`</span> <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a reference to a [`DOMMatrix`](dommatrix) object, which represents 4x4 matrices, suitable for 2D and 3D operations.

 <span class="page-not-created">`Window.DOMMatrixReadOnly`</span> <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a reference to a [`DOMMatrixReadOnly`](dommatrixreadonly) object, which represents 4x4 matrices, suitable for 2D and 3D operations.

 <span class="page-not-created">`Window.DOMPoint`</span> <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a reference to a [`DOMPoint`](dompoint) object, which represents a 2D or 3D point in a coordinate system.

 <span class="page-not-created">`Window.DOMPointReadOnly`</span> <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a reference to a [`DOMPointReadOnly`](dompointreadonly) object, which represents a 2D or 3D point in a coordinate system.

 <span class="page-not-created">`Window.DOMQuad`</span> <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a reference to a [`DOMQuad`](domquad) object, which provides represents a quadrilaterial object, that is one having four corners and four sides.

 <span class="page-not-created">`Window.DOMRect`</span> <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a reference to a [`DOMRect`](domrect) object, which represents a rectangle.

 <span class="page-not-created">`Window.DOMRectReadOnly`</span> <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a reference to a [`DOMRectReadOnly`](domrectreadonly) object, which represents a rectangle.

 [`Window.event`](window/event) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>   
Returns the **current event**, which is the event currently being handled by the JavaScript code's context, or `undefined` if no event is currently being handled. The [`Event`](event) object passed directly to event handlers should be used instead whenever possible.

 [`Window.frameElement`](window/frameelement) <span class="badge inline readonly">Read only </span>   
Returns the element in which the window is embedded, or null if the window is not embedded.

 [`Window.frames`](window/frames) <span class="badge inline readonly">Read only </span>   
Returns an array of the subframes in the current window.

[`Window.fullScreen`](window/fullscreen)  
This property indicates whether the window is displayed in full screen or not.

 [`Window.history`](window/history) <span class="badge inline readonly">Read only </span>   
Returns a reference to the history object.

 [`Window.innerHeight`](window/innerheight) <span class="badge inline readonly">Read only </span>   
Gets the height of the content area of the browser window including, if rendered, the horizontal scrollbar.

 [`Window.innerWidth`](window/innerwidth) <span class="badge inline readonly">Read only </span>   
Gets the width of the content area of the browser window including, if rendered, the vertical scrollbar.

 [`Window.isSecureContext`](window/issecurecontext) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span> <span class="badge inline readonly">Read only </span>   
Indicates whether a context is capable of using features that require secure contexts.

 [`Window.length`](window/length) <span class="badge inline readonly">Read only </span>   
Returns the number of frames in the window. See also [`window.frames`](window/frames).

[`Window.location`](window/location)  
Gets/sets the location, or current URL, of the window object.

 [`Window.locationbar`](window/locationbar) <span class="badge inline readonly">Read only </span>   
Returns the locationbar object, whose visibility can be toggled in the window.

 [`Window.localStorage`](window/localstorage) <span class="badge inline readonly">Read only </span>   
Returns a reference to the local storage object used to store data that may only be accessed by the origin that created it.

 [`Window.menubar`](window/menubar) <span class="badge inline readonly">Read only </span>   
Returns the menubar object, whose visibility can be toggled in the window.

 <span class="page-not-created">`Window.messageManager`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the [message manager](https://developer.mozilla.org/en-US/docs/The_message_manager) object for this window.

 [`Window.mozInnerScreenX`](window/mozinnerscreenx) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the horizontal (X) coordinate of the top-left corner of the window's viewport, in screen coordinates. This value is reported in CSS pixels. See `mozScreenPixelsPerCSSPixel` in <span class="page-not-created">`nsIDOMWindowUtils`</span> for a conversion factor to adapt to screen pixels if needed.

 [`Window.mozInnerScreenY`](window/mozinnerscreeny) <span class="badge inline readonly">Read only </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Returns the vertical (Y) coordinate of the top-left corner of the window's viewport, in screen coordinates. This value is reported in CSS pixels. See `mozScreenPixelsPerCSSPixel` for a conversion factor to adapt to screen pixels if needed.

[`Window.name`](window/name)  
Gets/sets the name of the window.

 [`Window.navigator`](window/navigator) <span class="badge inline readonly">Read only </span>   
Returns a reference to the navigator object.

[`Window.opener`](window/opener)  
Returns a reference to the window that opened this current window.

 [`Window.outerHeight`](window/outerheight) <span class="badge inline readonly">Read only </span>   
Gets the height of the outside of the browser window.

 [`Window.outerWidth`](window/outerwidth) <span class="badge inline readonly">Read only </span>   
Gets the width of the outside of the browser window.

 [`Window.pageXOffset`](window/scrollx) <span class="badge inline readonly">Read only </span>   
An alias for [`window.scrollX`](window/scrollx).

 [`Window.pageYOffset`](window/scrolly) <span class="badge inline readonly">Read only </span>   
An alias for [`window.scrollY`](window/scrolly)

 [`Window.parent`](window/parent) <span class="badge inline readonly">Read only </span>   
Returns a reference to the parent of the current window or subframe.

 [`Window.performance`](window/performance) <span class="badge inline readonly">Read only </span>   
Returns a [`Performance`](performance) object, which includes the [`timing`](performance/timing) and [`navigation`](performance/navigation) attributes, each of which is an object providing [performance-related](navigation_timing_api) data. See also [Using Navigation Timing](navigation_timing_api/using_navigation_timing) for additional information and examples.

 [`Window.personalbar`](window/personalbar) <span class="badge inline readonly">Read only </span>   
Returns the personalbar object, whose visibility can be toggled in the window.

 [`Window.screen`](window/screen) <span class="badge inline readonly">Read only </span>   
Returns a reference to the screen object associated with the window.

 [`Window.screenX`](window/screenx) and [`Window.screenLeft`](window/screenleft) <span class="badge inline readonly">Read only </span>   
Both properties return the horizontal distance from the left border of the user's browser viewport to the left side of the screen.

 [`Window.screenY`](window/screeny) and [`Window.screenTop`](window/screentop) <span class="badge inline readonly">Read only </span>   
Both properties return the vertical distance from the top border of the user's browser viewport to the top side of the screen.

 [`Window.scrollbars`](window/scrollbars) <span class="badge inline readonly">Read only </span>   
Returns the scrollbars object, whose visibility can be toggled in the window.

 [`Window.scrollMaxX`](window/scrollmaxx) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
The maximum offset that the window can be scrolled to horizontally, that is the document width minus the viewport width.

 [`Window.scrollMaxY`](window/scrollmaxy) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
The maximum offset that the window can be scrolled to vertically (i.e., the document height minus the viewport height).

 [`Window.scrollX`](window/scrollx) <span class="badge inline readonly">Read only </span>   
Returns the number of pixels that the document has already been scrolled horizontally.

 [`Window.scrollY`](window/scrolly) <span class="badge inline readonly">Read only </span>   
Returns the number of pixels that the document has already been scrolled vertically.

 [`Window.self`](window/self) <span class="badge inline readonly">Read only </span>   
Returns an object reference to the window object itself.

[`Window.sessionStorage`](window/sessionstorage)  
Returns a reference to the session storage object used to store data that may only be accessed by the origin that created it.

 [`Window.sidebar`](window/sidebar) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="badge inline readonly">Read only </span>   
Returns a reference to the window object of the sidebar.

 [`Window.speechSynthesis`](window/speechsynthesis) <span class="badge inline readonly">Read only </span>   
Returns a [`SpeechSynthesis`](speechsynthesis) object, which is the entry point into using [Web Speech API](web_speech_api) speech synthesis functionality.

 [`Window.status`](window/status) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Gets/sets the text in the statusbar at the bottom of the browser.

 [`Window.statusbar`](window/statusbar) <span class="badge inline readonly">Read only </span>   
Returns the statusbar object, whose visibility can be toggled in the window.

 [`Window.toolbar`](window/toolbar) <span class="badge inline readonly">Read only </span>   
Returns the toolbar object, whose visibility can be toggled in the window.

 [`Window.top`](window/top) <span class="badge inline readonly">Read only </span>   
Returns a reference to the topmost window in the window hierarchy. This property is read only.

 [`Window.visualViewport`](window/visualviewport) <span class="badge inline readonly">Read only </span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Returns a [`VisualViewport`](visualviewport) object which represents the visual viewport for a given window.

 [`Window.window`](window/window) <span class="badge inline readonly">Read only </span>   
Returns a reference to the current window.

 `window[0]`, `window[1]`, etc.  
Returns a reference to the `window` object in the frames. See [`Window.frames`](window/frames) for more details.

### Properties implemented from elsewhere

 [`WindowOrWorkerGlobalScope.caches`](windoworworkerglobalscope/caches) <span class="badge inline readonly">Read only </span>   
Returns the [`CacheStorage`](cachestorage) object associated with the current context. This object enables functionality such as storing assets for offline use, and generating custom responses to requests.

 [`WindowOrWorkerGlobalScope.indexedDB`](windoworworkerglobalscope/indexeddb) <span class="badge inline readonly">Read only </span>   
Provides a mechanism for applications to asynchronously access capabilities of indexed databases; returns an [`IDBFactory`](idbfactory) object.

 [`WindowOrWorkerGlobalScope.isSecureContext`](windoworworkerglobalscope/issecurecontext) <span class="badge inline readonly">Read only </span>   
Returns a boolean indicating whether the current context is secure (`true`) or not (`false`).

 [`WindowOrWorkerGlobalScope.origin`](windoworworkerglobalscope/origin) <span class="badge inline readonly">Read only </span>   
Returns the global object's origin, serialized as a string. (This does not yet appear to be implemented in any browser.)

### Deprecated properties

 [`Window.content`](window/content) and `Window._content` <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>   
Returns a reference to the content element in the current window. Since Firefox 57 (initially Nightly-only), both versions are only available from chrome (privileged) code, and not available to the web anymore.

 [`Window.defaultStatus`](window/defaultstatus) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Gets/sets the status bar text for the given window.

 [`Window.dialogArguments`](window/dialogarguments) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span> <span class="badge inline readonly">Read only </span>   
Gets the arguments passed to the window (if it's a dialog box) at the time [`window.showModalDialog()`](window/showmodaldialog) was called. This is an <span class="page-not-created">`nsIArray`</span>.

 [`Window.directories`](window/directories) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Synonym of [`window.personalbar`](window/personalbar)

 <span class="page-not-created">`Window.globalStorage`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Multiple storage objects that were used for storing data across multiple pages.

 [`Window.mozAnimationStartTime`](window/mozanimationstarttime) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The time in milliseconds since epoch at which the current animation cycle began. Use [`Animation.startTime`](animation/starttime) instead.

 [`Window.mozPaintCount`](window/mozpaintcount) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns the number of times the current document has been rendered to the screen in this window. This can be used to compute rendering performance.

 [`Window.orientation`](window/orientation) <span class="badge inline readonly">Read only </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns the orientation in degrees (in 90 degree increments) of the viewport relative to the device's natural orientation.

 [`Window.pkcs11`](window/pkcs11) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Formerly provided access to install and remove PKCS11 modules.

 <span class="page-not-created">`Window.returnValue`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The return value to be returned to the function that called [`window.showModalDialog()`](window/showmodaldialog) to display the window as a modal dialog.

Methods
-------

*This interface inherits methods from the [`EventTarget`](eventtarget) interface and implements methods from [`WindowOrWorkerGlobalScope`](windoworworkerglobalscope) and [`EventTarget`](eventtarget).*

[`Window.alert()`](window/alert)  
Displays an alert dialog.

[`Window.blur()`](window/blur)  
Sets focus away from the window.

 [`Window.cancelAnimationFrame()`](window/cancelanimationframe) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Enables you to cancel a callback previously scheduled with [`Window.requestAnimationFrame`](window/requestanimationframe).

 [`Window.cancelIdleCallback()`](window/cancelidlecallback) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Enables you to cancel a callback previously scheduled with [`Window.requestIdleCallback`](window/requestidlecallback).

[`Window.clearImmediate()`](window/clearimmediate)  
Cancels the repeated execution set using `setImmediate`.

[`Window.close()`](window/close)  
Closes the current window.

[`Window.confirm()`](window/confirm)  
Displays a dialog with a message that the user needs to respond to.

 [`Window.dump()`](window/dump) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Writes a message to the console.

[`Window.find()`](window/find)  
Searches for a given string in a window.

[`Window.focus()`](window/focus)  
Sets focus on the current window.

[`Window.getComputedStyle()`](window/getcomputedstyle)  
Gets computed style for the specified element. Computed style indicates the computed values of all CSS properties of the element.

 [`Window.getDefaultComputedStyle()`](window/getdefaultcomputedstyle) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Gets default computed style for the specified element, ignoring author stylesheets.

[`Window.getSelection()`](window/getselection)  
Returns the selection object representing the selected item(s).

[`Window.matchMedia()`](window/matchmedia)  
Returns a [`MediaQueryList`](mediaquerylist) object representing the specified media query string.

<span class="page-not-created">`Window.maximize()`</span>  
[`Window.minimize()`](window/minimize) (top-level XUL windows only)  
Minimizes the window.

[`Window.moveBy()`](window/moveby)  
Moves the current window by a specified amount.

[`Window.moveTo()`](window/moveto)  
Moves the window to the specified coordinates.

[`Window.open()`](window/open)  
Opens a new window.

[`Window.postMessage()`](window/postmessage)  
Provides a secure means for one window to send a string of data to another window, which need not be within the same domain as the first.

[`Window.print()`](window/print)  
Opens the Print Dialog to print the current document.

[`Window.prompt()`](window/prompt)  
Returns the text entered by the user in a prompt dialog.

[`Window.requestAnimationFrame()`](window/requestanimationframe)  
Tells the browser that an animation is in progress, requesting that the browser schedule a repaint of the window for the next animation frame.

 [`Window.requestIdleCallback()`](window/requestidlecallback) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Enables the scheduling of tasks during a browser's idle periods.

[`Window.resizeBy()`](window/resizeby)  
Resizes the current window by a certain amount.

[`Window.resizeTo()`](window/resizeto)  
Dynamically resizes window.

[`Window.scroll()`](window/scroll)  
Scrolls the window to a particular place in the document.

[`Window.scrollBy()`](window/scrollby)  
Scrolls the document in the window by the given amount.

 [`Window.scrollByLines()`](window/scrollbylines) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Scrolls the document by the given number of lines.

 [`Window.scrollByPages()`](window/scrollbypages) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Scrolls the current document by the specified number of pages.

[`Window.scrollTo()`](window/scrollto)  
Scrolls to a particular set of coordinates in the document.

[`Window.setImmediate()`](window/setimmediate)  
Executes a function after the browser has finished other heavy tasks

 <span class="page-not-created">`Window.setResizable()`</span> <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Toggles a user's ability to resize a window.

 [`Window.sizeToContent()`](window/sizetocontent) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Sizes the window according to its content.

[`Window.showOpenFilePicker()`](window/showopenfilepicker)  
Shows a file picker that allows a user to select a file or multiple files.

[`Window.showSaveFilePicker()`](window/showsavefilepicker)  
Shows a file picker that allows a user to save a file.

[`Window.showDirectoryPicker()`](window/showdirectorypicker)  
Displays a directory picker which allows the user to select a directory.

[`Window.stop()`](window/stop)  
This method stops window loading.

 [`Window.updateCommands()`](window/updatecommands) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
Updates the state of commands of the current chrome window (UI).

### Methods implemented from elsewhere

[`EventTarget.addEventListener()`](eventtarget/addeventlistener)  
Register an event handler to a specific event type on the window.

[`EventTarget.dispatchEvent()`](eventtarget/dispatchevent)  
Used to trigger an event.

[`WindowOrWorkerGlobalScope.atob()`](windoworworkerglobalscope/atob)  
Decodes a string of data which has been encoded using base-64 encoding.

[`WindowOrWorkerGlobalScope.btoa()`](windoworworkerglobalscope/btoa)  
Creates a base-64 encoded ASCII string from a string of binary data.

[`WindowOrWorkerGlobalScope.clearInterval()`](windoworworkerglobalscope/clearinterval)  
Cancels the repeated execution set using [`WindowOrWorkerGlobalScope.setInterval()`](windoworworkerglobalscope/setinterval).

[`WindowOrWorkerGlobalScope.clearTimeout()`](windoworworkerglobalscope/cleartimeout)  
Cancels the delayed execution set using [`WindowOrWorkerGlobalScope.setTimeout()`](windoworworkerglobalscope/settimeout).

[`WindowOrWorkerGlobalScope.createImageBitmap()`](windoworworkerglobalscope/createimagebitmap)  
Accepts a variety of different image sources, and returns a [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) which resolves to an [`ImageBitmap`](imagebitmap). Optionally the source is cropped to the rectangle of pixels originating at *(sx, sy)* with width sw, and height sh.

[`WindowOrWorkerGlobalScope.fetch()`](windoworworkerglobalscope/fetch)  
Starts the process of fetching a resource from the network.

[`EventTarget.removeEventListener`](eventtarget/removeeventlistener)  
Removes an event listener from the window.

[`WindowOrWorkerGlobalScope.setInterval()`](windoworworkerglobalscope/setinterval)  
Schedules a function to execute every time a given number of milliseconds elapses.

[`WindowOrWorkerGlobalScope.setTimeout()`](windoworworkerglobalscope/settimeout)  
Schedules a function to execute in a given amount of time.

### Deprecated methods

 [`Window.back()`](window/back) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Moves back one in the window history. This method is deprecated; you should instead use [`window.history.back()`](history/back).

 [`Window.captureEvents()`](window/captureevents) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Registers the window to capture all events of the specified type.

 [`Window.forward()`](window/forward) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Moves the window one document forward in the history. This method is deprecated; you should instead use [`window.history.forward()`](history/forward).

 [`Window.home()`](window/home) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Returns the browser to the home page.

 [`Window.openDialog()`](window/opendialog) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Opens a new dialog window.

 [`Window.releaseEvents()`](window/releaseevents) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Releases the window from trapping events of a specific type.

 [`Window.showModalDialog()`](window/showmodaldialog) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Displays a modal dialog.

Event handlers
--------------

These are properties of the window object that can be set to establish event handlers for the various things that can happen in the window that might be of interest.

*This interface inherits event handlers from the [`EventTarget`](eventtarget) interface and implements event handlers from [`WindowEventHandlers`](windoweventhandlers).*

[`Window.onappinstalled`](window/onappinstalled)  
Called when the page is installed as a webapp. See [`appinstalled`](window/appinstalled_event) event.

[`Window.onbeforeinstallprompt`](window/onbeforeinstallprompt)  
An event handler property dispatched before a user is prompted to save a web site to a home screen on mobile.

 `Window.ondevicelight` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An event handler property for any ambient light levels changes (see [`DeviceLightEvent`](devicelightevent)).

[`Window.ondevicemotion`](window/ondevicemotion)  
Called if accelerometer detects a change (For mobile devices)

[`Window.ondeviceorientation`](window/ondeviceorientation)  
Called when the orientation is changed (For mobile devices)

 [`Window.ondeviceorientationabsolute`](window/ondeviceorientationabsolute) <span class="icon non-standard" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This API has not been standardized. </span>   
An event handler property for any device orientation changes.

 `Window.ondeviceproximity` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An event handler property for device proximity event (see [`DeviceProximityEvent`](deviceproximityevent))

[`Window.ongamepadconnected`](window/ongamepadconnected)  
Represents an event handler that will run when a gamepad is connected (when the `gamepadconnected` event fires).

[`Window.ongamepaddisconnected`](window/ongamepaddisconnected)  
Represents an event handler that will run when a gamepad is disconnected (when the `gamepaddisconnected` event fires).

[`Window.onmozbeforepaint`](window/onmozbeforepaint)  
An event handler property for the `MozBeforePaint` event, which is sent before repainting the window if the event has been requested by a call to the [`window.requestAnimationFrame`](window/requestanimationframe) method.

[`Window.onpaint`](window/onpaint)  
An event handler property for paint events on the window.

[`WindowEventHandlers.onrejectionhandled`](windoweventhandlers/onrejectionhandled)  
An event handler for handled [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) rejection events.

 `Window.onuserproximity` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
An event handler property for user proximity events (see [`UserProximityEvent`](userproximityevent)).

[`Window.onvrdisplayconnect`](window/onvrdisplayconnect)  
Represents an event handler that will run when a compatible VR device has been connected to the computer (when the `vrdisplayconnected` event fires).

[`Window.onvrdisplaydisconnect`](window/onvrdisplaydisconnect)  
Represents an event handler that will run when a compatible VR device has been disconnected from the computer (when the `vrdisplaydisconnected` event fires).

[`Window.onvrdisplayactivate`](window/onvrdisplayactivate)  
Represents an event handler that will run when a display is able to be presented to (when the `vrdisplayactivate` event fires), for example if an HMD has been moved to bring it out of standby, or woken up by being put on.

[`Window.onvrdisplaydeactivate`](window/onvrdisplaydeactivate)  
Represents an event handler that will run when a display can no longer be presented to (when the `vrdisplaydeactivate` event fires), for example if an HMD has gone into standby or sleep mode due to a period of inactivity.

[`Window.onvrdisplayblur`](window/onvrdisplayblur)  
Represents an event handler that will run when presentation to a display has been paused for some reason by the browser, OS, or VR hardware (when the `vrdisplayblur` event fires) — for example, while the user is interacting with a system menu or browser, to prevent tracking or loss of experience.

[`Window.onvrdisplayfocus`](window/onvrdisplayfocus)  
Represents an event handler that will run when presentation to a display has resumed after being blurred (when the `vrdisplayfocus` event fires).

[`Window.onvrdisplaypresentchange`](window/onvrdisplaypresentchange)  
represents an event handler that will run when the presenting state of a VR device changes — i.e. goes from presenting to not presenting, or vice versa (when the `vrdisplaypresentchange` event fires).

### Event handlers implemented from elsewhere

[`GlobalEventHandlers.onabort`](globaleventhandlers/onabort)  
Called when the loading of a resource has been aborted, such as by a user canceling the load while it is still in progress

[`WindowEventHandlers.onafterprint`](windoweventhandlers/onafterprint)  
Called when the print dialog box is closed. See `afterprint` event.

[`WindowEventHandlers.onbeforeprint`](windoweventhandlers/onbeforeprint)  
Called when the print dialog box is opened. See `beforeprint` event.

[`WindowEventHandlers.onbeforeunload`](windoweventhandlers/onbeforeunload)  
An event handler property for before-unload events on the window.

[`GlobalEventHandlers.onblur`](globaleventhandlers/onblur)  
Called after the window loses focus, such as due to a popup.

[`GlobalEventHandlers.onchange`](globaleventhandlers/onchange)  
An event handler property for change events on the window.

[`GlobalEventHandlers.onclick`](globaleventhandlers/onclick)  
Called after the ANY mouse button is pressed & released

[`GlobalEventHandlers.ondblclick`](globaleventhandlers/ondblclick)  
Called when a double click is made with ANY mouse button.

[`GlobalEventHandlers.onclose`](globaleventhandlers/onclose)  
Called after the window is closed

[`GlobalEventHandlers.oncontextmenu`](globaleventhandlers/oncontextmenu)  
Called when the RIGHT mouse button is pressed

[`GlobalEventHandlers.onerror`](globaleventhandlers/onerror)  
Called when a resource fails to load OR when an error occurs at runtime. See `error` event.

[`GlobalEventHandlers.onfocus`](globaleventhandlers/onfocus)  
Called after the window receives or regains focus. See `focus` events.

[`WindowEventHandlers.onhashchange`](windoweventhandlers/onhashchange)  
An event handler property for `hashchange` events on the window; called when the part of the URL after the hash mark ("\#") changes.

[`GlobalEventHandlers.oninput`](globaleventhandlers/oninput)  
Called when the value of an &lt;input&gt; element changes

[`GlobalEventHandlers.onkeydown`](globaleventhandlers/onkeydown)  
Called when you begin pressing ANY key. See `keydown` event.

[`GlobalEventHandlers.onkeypress`](globaleventhandlers/onkeypress)  
Called when a key (except Shift, Fn, and CapsLock) is in pressed position. See `keypress` event.

[`GlobalEventHandlers.onkeyup`](globaleventhandlers/onkeyup)  
Called when you finish releasing ANY key. See `keyup` event.

[`WindowEventHandlers.onlanguagechange`](windoweventhandlers/onlanguagechange)  
An event handler property for `languagechange` events on the window.

[`GlobalEventHandlers.onload`](globaleventhandlers/onload)  
Called after all resources and the DOM are fully loaded. WILL NOT get called when the page is loaded from cache, such as with back button.

[`WindowEventHandlers.onmessage`](windoweventhandlers/onmessage)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `message` event is raised.

[`GlobalEventHandlers.onmousedown`](globaleventhandlers/onmousedown)  
Called when ANY mouse button is pressed.

[`GlobalEventHandlers.onmousemove`](globaleventhandlers/onmousemove)  
Called continously when the mouse is moved inside the window.

[`GlobalEventHandlers.onmouseout`](globaleventhandlers/onmouseout)  
Called when the pointer leaves the window.

[`GlobalEventHandlers.onmouseover`](globaleventhandlers/onmouseover)  
Called when the pointer enters the window

[`GlobalEventHandlers.onmouseup`](globaleventhandlers/onmouseup)  
Called when ANY mouse button is released

<span class="page-not-created">`WindowEventHandlers.onoffline`</span>  
Called when network connection is lost. See `offline` event.

<span class="page-not-created">`WindowEventHandlers.ononline`</span>  
Called when network connection is established. See `online` event.

<span class="page-not-created">`WindowEventHandlers.onpagehide`</span>  
Called when the user navigates away from the page, before the onunload event. See `pagehide` event.

<span class="page-not-created">`WindowEventHandlers.onpageshow`</span>  
Called after all resources and the DOM are fully loaded. See `pageshow` event.

[`WindowEventHandlers.onpopstate`](windoweventhandlers/onpopstate)  
Called when a back button is pressed.

[`GlobalEventHandlers.onreset`](globaleventhandlers/onreset)  
Called when a form is reset

[`GlobalEventHandlers.onresize`](globaleventhandlers/onresize)  
Called continuously as you are resizing the window.

[`GlobalEventHandlers.onscroll`](globaleventhandlers/onscroll)  
Called when the scroll bar is moved via ANY means. If the resource fully fits in the window, then this event cannot be invoked

[`GlobalEventHandlers.onwheel`](globaleventhandlers/onwheel)  
Called when the mouse wheel is rotated around any axis

[`GlobalEventHandlers.onselect`](globaleventhandlers/onselect)  
Called after text in an input field is selected

[`GlobalEventHandlers.onselectionchange`](globaleventhandlers/onselectionchange)  
Is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) representing the code to be called when the `selectionchange` event is raised.

[`WindowEventHandlers.onstorage`](windoweventhandlers/onstorage)  
Called when there is a change in session storage or local storage. See `storage` event

[`GlobalEventHandlers.onsubmit`](globaleventhandlers/onsubmit)  
Called when a form is submitted

 [`WindowEventHandlers.onunhandledrejection`](windoweventhandlers/onunhandledrejection) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
An event handler for unhandled [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) rejection events.

[`WindowEventHandlers.onunload`](windoweventhandlers/onunload)  
Called when the user navigates away from the page.

Events
------

Listen to these events using `addEventListener()` or by assigning an event listener to the `oneventname` property of this interface.

[`error`](window/error_event)  
Fired when a resource failed to load, or can't be used. For example, if a script has an execution error or an image can't be found or is invalid.  
Also available via the [`onerror`](globaleventhandlers/onerror) property.

[`languagechange`](window/languagechange_event)  
Fired at the global scope object when the user's preferred language changes.  
Also available via the [`onlanguagechange`](windoweventhandlers/onlanguagechange) property.

 [`orientationchange`](window/orientationchange_event) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Fired when the orientation of the device has changed.  
Also available via the <span class="page-not-created">`onorientationchange`</span> property.

[`devicemotion`](window/devicemotion_event)  
Fired at a regular interval, indicating the amount of physical force of acceleration the device is receiving and the rate of rotation, if available.

[`deviceorientation`](window/deviceorientation_event)  
Fired when fresh data is available from the magnetometer orientation sensor about the current orientation of the device as compared to the Earth coordinate frame.

[`resize`](window/resize_event)  
Fired when the window has been resized.  
Also available via the [`onresize`](globaleventhandlers/onresize) property.

[`storage`](window/storage_event)  
Fired when a storage area (`localStorage` or `sessionStorage`) has been modified in the context of another document.  
Also available via the [`onstorage`](windoweventhandlers/onstorage) property.

### Animation events

[`animationcancel`](window/animationcancel_event)  
Fired when an animation unexpectedly aborts.  
Also available via the [`onanimationcancel`](globaleventhandlers/onanimationcancel) property.

[`animationend`](window/animationend_event)  
Fired when an animation has completed normally.  
Also available via the [`onanimationend`](globaleventhandlers/onanimationend) property.

[`animationiteration`](window/animationiteration_event)  
Fired when an animation iteration has completed.  
Also available via the [`onanimationiteration`](globaleventhandlers/onanimationiteration) property.

[`animationstart`](window/animationstart_event)  
Fired when an animation starts.  
Also available via the [`onanimationstart`](globaleventhandlers/onanimationstart) property.

### Clipboard events

[`copy`](window/copy_event)  
Fired when the user initiates a copy action through the browser's user interface.  
Also available via the [`oncopy`](htmlelement/oncopy) property.

[`cut`](window/cut_event)  
Fired when the user initiates a cut action through the browser's user interface.  
Also available via the [`oncut`](htmlelement/oncut) property.

[`paste`](window/paste_event)  
Fired when the user initiates a paste action through the browser's user interface.  
Also available via the [`onpaste`](htmlelement/onpaste) property.

### Connection events

[`offline`](window/offline_event)  
Fired when the browser has lost access to the network and the value of `navigator.onLine` has switched to `false`.  
Also available via the <span class="page-not-created">`onoffline`</span> property.

[`online `](window/online_event)  
Fired when the browser has gained access to the network and the value of `navigator.onLine` has switched to `true`.  
Also available via the <span class="page-not-created">`ononline`</span> property.

### Focus events

[`blur`](window/blur_event)  
Fired when an element has lost focus.  
Also available via the [`onblur`](globaleventhandlers/onblur) property.

[`focus`](window/focus_event)  
Fired when an element has gained focus.  
Also available via the [`onfocus`](globaleventhandlers/onfocus) property

### Gamepad events

[`gamepadconnected`](window/gamepadconnected_event)  
Fired when the browser detects that a gamepad has been connected or the first time a button/axis of the gamepad is used.  
Also available via the [`ongamepadconnected`](window/ongamepadconnected) property.

[`gamepaddisconnected`](window/gamepaddisconnected_event)  
Fired when the browser detects that a gamepad has been disconnected.  
Also available via the [`ongamepaddisconnected`](window/ongamepaddisconnected) property

### History events

[`hashchange`](window/hashchange_event)  
Fired when the fragment identifier of the URL has changed (the part of the URL beginning with and following the `#` symbol).  
Also available via the [`onhashchange`](windoweventhandlers/onhashchange) property.

[`pagehide`](window/pagehide_event)  
Sent when the browser hides the current document while in the process of switching to displaying in its place a different document from the session's history. This happens, for example, when the user clicks the Back button or when they click the Forward button to move ahead in session history.  
Also available through the `onpagehide` event handler property.

[`pageshow`](window/pageshow_event)  
Sent when the browser makes the document visible due to navigation tasks, including not only when the page is first loaded, but also situations such as the user navigating back to the page after having navigated to another within the same tab.  
Also available using the `onpageshow` event handler property.

`popstate`  
Fired when the active history entry changes.  
Also available using the [`onpopstate`](windoweventhandlers/onpopstate) event handler property.

### Load & unload events

[`beforeunload`](window/beforeunload_event)  
Fired when the window, the document and its resources are about to be unloaded.  
Also available via the [`onbeforeunload`](windoweventhandlers/onbeforeunload) property.

[`DOMContentLoaded`](window/domcontentloaded_event)  
Fired when the document has been completely loaded and parsed, without waiting for stylesheets, images, and subframes to finish loading.

[`load`](window/load_event)  
Fired when the whole page has loaded, including all dependent resources such as stylesheets images.  
Also available via the [`onload`](globaleventhandlers/onload) property.

[`unload`](window/unload_event)  
Fired when the document or a child resource is being unloaded.  
Also available via the [`onunload`](windoweventhandlers/onunload) property.

### Manifest events

[`appinstalled`](window/appinstalled_event)  
Fired when the browser has successfully installed a page as an application.  
Also available via the [`onappinstalled`](window/onappinstalled) property.

<span class="page-not-created">`beforeinstallprompt`</span>  
Fired when a user is about to be prompted to install a web application.  
Also available via the [`onbeforeinstallprompt`](window/onbeforeinstallprompt) property.

### Messaging events

[`message`](window/message_event)  
Fired when the window receives a message, for example from a call to [`Window.postMessage()`](window/postmessage) from another browsing context.  
Also available via the [`onmessage`](windoweventhandlers/onmessage) property.

[`messageerror`](window/messageerror_event)  
Fired when a `Window` object receives a message that can't be deserialized.  
Also available via the [`onmessageerror`](windoweventhandlers/onmessageerror) property.

### Print events

[`afterprint`](window/afterprint_event)  
Fired after the associated document has started printing or the print preview has been closed.  
Also available via the [`onafterprint`](windoweventhandlers/onafterprint) property.

[`beforeprint`](window/beforeprint_event)  
Fired when the associated document is about to be printed or previewed for printing.  
Also available via the [`onbeforeprint`](windoweventhandlers/onbeforeprint) property.

### Promise rejection events

[`rejectionhandled`](window/rejectionhandled_event)  
Sent every time a JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is rejected, regardless of whether or not there is a handler in place to catch the rejection.  
Also available through the [`onrejectionhandled`](windoweventhandlers/onrejectionhandled) event handler property.

[`unhandledrejection`](window/unhandledrejection_event)  
Sent when a JavaScript [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) is rejected but there is no handler in place to catch the rejection.  
Also available using the [`onunhandledrejection`](windoweventhandlers/onunhandledrejection) event handler property.

### Transition events

[`transitioncancel`](window/transitioncancel_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is canceled.  
Also available via the [`ontransitioncancel`](globaleventhandlers/ontransitioncancel) property.

[`transitionend`](window/transitionend_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has completed.  
Also available via the [`ontransitionend`](globaleventhandlers/ontransitionend) property.

[`transitionrun`](window/transitionrun_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) is first created.  
Also available via the <span class="page-not-created">`ontransitionrun`</span> property.

[`transitionstart`](window/transitionstart_event)  
Fired when a [CSS transition](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions) has actually started.  
Also available via the <span class="page-not-created">`ontransitionstart`</span> property.

### WebVR events

[`vrdisplayactivate`](window/vrdisplayactivate_event)  
Fired when a VR display becomes available to be presented to, for example if an HMD has been moved to bring it out of standby, or woken up by being put on.  
Also available via the [`onvrdisplayactivate`](window/onvrdisplayactivate) property.

[`vrdisplayblur`](window/vrdisplayblur_event)  
Fired when presentation to a VR display has been paused for some reason by the browser, OS, or VR hardware.  
Also available via the [`onvrdisplayblur`](window/onvrdisplayblur) property.

[`vrdisplayconnect`](window/vrdisplayconnect_event)  
Fired when a compatible VR display is connected to the computer.  
Also available via the [`onvrdisplayconnect`](window/onvrdisplayconnect) property.

[`vrdisplaydeactivate`](window/vrdisplaydeactivate_event)  
Fired when a VR display can no longer be presented to, for example if an HMD has gone into standby or sleep mode due to a period of inactivity.  
Also available via the [`onvrdisplaydeactivate`](window/onvrdisplaydeactivate) property.

[`vrdisplaydisconnect`](window/vrdisplaydisconnect_event)  
Fired when a compatible VR display is disconnected from the computer.  
Also available via the [`onvrdisplaydisconnect`](window/onvrdisplaydisconnect) property.

[`vrdisplayfocus`](window/vrdisplayfocus_event)  
Fired when presentation to a VR display has resumed after being blurred.  
Also available via the [`onvrdisplayfocus`](window/onvrdisplayfocus) property.

[`vrdisplaypresentchange`](window/vrdisplaypresentchange_event)  
Fired when the presenting state of a VR display changes — i.e. goes from presenting to not presenting, or vice versa.  
Also available via the [`onvrdisplaypresentchange`](window/onvrdisplaypresentchange) property.

[`vrdisplaypointerrestricted`](window/vrdisplaypointerrestricted_event)  
Fired when the VR display's pointer input is restricted to consumption via a [pointerlocked element](pointer_lock_api).  
Also available via the [`onvrdisplaypointerrestricted`](window/onvrdisplaypointerrestricted) property.

[`vrdisplaypointerunrestricted`](window/vrdisplaypointerunrestricted_event)  
Fired when the VR display's pointer input is no longer restricted to consumption via a [pointerlocked element](pointer_lock_api).  
Also available via the [`onvrdisplaypointerunrestricted`](window/onvrdisplaypointerunrestricted) property.

Interfaces
----------

See [DOM Reference](document_object_model).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#the-window-object">HTML Living Standard<br />
<span class="small">The definition of 'Window' in that specification.</span></a></td></tr></tbody></table>

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

`Window`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`DOMContentLoaded_event`

1

12

1

9

9

3.1

1

18

4

10.1

2

1.0

`afterprint_event`

63

12

6

Yes

50

13

63

63

?

46

13

8.0

`alert`

1

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

12

1

4

3

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1

1

Starting with WebView 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

18

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

4

10.1

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1

1.0

Starting with Samsung Internet 5.0, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

`animationcancel_event`

No

No

54

?

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

1

≤79

≤79

Yes

?

?

9

43

1

43

18

Yes

?

9

4.0

1.0

`animationiteration_event`

43

1

≤79

≤79

51

?

?

9

43

1

43

18

51

?

9

4.0

1.0

`animationstart_event`

43

1

≤79

≤79

51

?

?

9

43

1

43

18

51

?

9

4.0

1.0

`beforeprint_event`

63

12

6

Yes

50

13

63

63

?

46

13

8.0

`beforeunload_event`

1

12

1

4

12

3

1

18

4

12

1

1.0

`blur`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`blur_event`

5

12

Yes

Apart from firing the event on `window` as other browsers do, Firefox also fires the event on the `document` object. See [bug 1228802](https://bugzil.la/1228802).

Yes-24

The interface for this event is [`Event`](https://developer.mozilla.org/docs/Web/API/Event), not [`FocusEvent`](https://developer.mozilla.org/docs/Web/API/FocusEvent).

Yes

12.1

5.1

≤37

18

Yes

12.1

5.1

1.0

`cancelAnimationFrame`

24

12

23

11-23

10

15

6.1

6-6.1

≤37

25

23

14-23

14

7

1.5

`cancelIdleCallback`

47

79

55

No

Yes

No

47

47

55

Yes

No

5.0

`captureEvents`

1

12

1

11

≤12.1

1

1

18

4

≤12.1

1

1.0

`clearImmediate`

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

`close`

1

12

Before Edge 79, scripts can close windows that weren't opened by the same script.

1

Before Firefox 46, scripts can close windows that weren't opened by the same script.

4

3

1

1

18

4

Before Firefox 46, scripts can close windows that weren't opened by the same script.

10.1

1

1.0

`closed`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`confirm`

1

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

12

1

4

3

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1

1

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

18

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

4

10.1

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1

1.0

Starting with Samsung Internet 5.0, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

`convertPointFromNodeToPage`

Yes-39

No

No

No

Yes-26

Yes

Yes-39

Yes-39

No

Yes-26

Yes

Yes-4.0

`convertPointFromPageToNode`

Yes-39

No

No

No

Yes-26

Yes

Yes-39

Yes-39

No

Yes-26

Yes

Yes-4.0

`cookieStore`

87

87

No

No

73

No

87

87

No

No

No

14.0

`copy_event`

1

≤18

Yes

No

15

Yes

1

18

Yes

14

?

1.0

`crypto`

37

12

1

11

24

6.1

37

37

4

24

6.1

3.0

`customElements`

54

79

63

No

41

10.1

54

54

63

41

10.3

6.0

`cut_event`

1

≤18

Yes

No

15

Yes

1

18

Yes

14

?

1.0

`devicemotion_event`

Yes

≤18

6

?

Yes

?

Yes

Yes

6

No

4.2

Yes

`deviceorientation_event`

7

≤18

6

3.6-6

?

12

Yes

3

18

6

4-6

12

4.2

1.0

`devicePixelRatio`

1

12

18

11

11.1

3

1

18

18

11.1

1

1.0

`dialogArguments`

?

?

No

No

?

No

?

?

No

?

No

?

`document`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

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

`event`

1

12

66

4

7

1.1

1

18

66

10.1

1

1.0

`external`

Yes

12

2

From Firefox 78 `AddSearchProvider()` does nothing, as the specification requires.

4

15

No

Yes

Yes

4

From Firefox for Android 79 `AddSearchProvider()` does nothing, as the specification requires.

14

No

Yes

`find`

1

79

1

No

15

3

1

18

4

14

1

1.0

`focus`

1

Starting in Chrome 66, opening a popup in fullscreen mode and calling this function will end fullscreen mode.

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`focus_event`

Yes

12

Yes

Apart from firing the event on `window` as other browsers do, Firefox also fires the event on the `document` object. See [bug 1228802](https://bugzil.la/1228802).

Yes-24

The interface for this event is [`Event`](https://developer.mozilla.org/docs/Web/API/Event), not [`FocusEvent`](https://developer.mozilla.org/docs/Web/API/FocusEvent).

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`frameElement`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`frames`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`fullScreen`

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

`gamepadconnected_event`

35

21-35

≤18

29

No

22

15-22

10.1

37

37

32

Yes

No

3.0

`gamepaddisconnected_event`

35

21-35

≤18

29

No

22

15-22

10.1

37

37

32

Yes

No

3.0

`getComputedStyle`

1

12

1

Before version 62 this function returned `null` when called on a Window with no presentation (e.g. an iframe with `display: none;` set). Since 62 it returns a `CSSStyleDeclaration` object with `length` 0, containing empty strings ([bug 1467722](https://bugzil.la/1467722); also see [bug 1471231](https://bugzil.la/1471231) for further work).

9

7.2

3

1

18

4

Before version 62 this function returned `null` when called on a Window with no presentation (e.g. an iframe with `display: none;` set). Since 62 it returns a `CSSStyleDeclaration` object with `length` 0, containing empty strings ([bug 1467722](https://bugzil.la/1467722); also see [bug 1471231](https://bugzil.la/1471231) for further work).

10.1

1

1.0

`getDefaultComputedStyle`

No

No

19

No

No

No

No

No

19

No

No

No

`getSelection`

1

12

1

9

9

1

1

18

4

10.1

1

1.0

`globalStorage`

No

No

2-13

No

?

No

No

No

4-14

?

No

No

`hashchange_event`

5

12

3.6

8

10.6

5

≤37

18

4

11

5

1.0

`history`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`home`

No

No

1-32

No

≤12.1-15

No

No

No

4-32

?

No

No

`innerHeight`

1

12

1

4-24

This property was buggy and could give a wrong value before page load in certain circumstances, see [bug 641188](https://bugzil.la/641188).

9

9

3

1

18

4

4-24

This property was buggy and could give a wrong value before page load in certain circumstances, see [bug 641188](https://bugzil.la/641188).

10.1

1

This property returns the height of the [visual viewport](https://developer.mozilla.org/docs/Glossary/visual_viewport) instead of the layout viewport. See [this bug](https://webkit.org/b/174362) for details.

1.0

`innerWidth`

1

12

1

4-24

This property was buggy and could give a wrong value before page load in certain circumstances, see [bug 641188](https://bugzil.la/641188).

9

9

3

1

18

4

4-24

This property was buggy and could give a wrong value before page load in certain circumstances, see [bug 641188](https://bugzil.la/641188).

10.1

1

This property returns the width of the [visual viewport](https://developer.mozilla.org/docs/Glossary/visual_viewport) instead of the layout viewport. See [this bug](https://webkit.org/b/174362) for details.

1.0

`isSecureContext`

47

15

49

No

34

11.1

47

47

49

34

11.3

5.0

`languagechange_event`

37

≤79

32

No

24

?

37

37

4

24

?

4.0

`length`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`load_event`

1

12

1

4

4

1.3

1

18

4

10.1

1

1.0

`localStorage`

4

12

3.5

8

10.5

4

≤37

18

4

11

3.2

1.0

`location`

1

12

1

Before Firefox 57, single quotes contained in URLs were escaped when accessed via URL APIs. See [bug 1386683](https://bugzil.la/1386683).

4

3

1

1

18

4

Before Firefox 57, single quotes contained in URLs were escaped when accessed via URL APIs. See [bug 1386683](https://bugzil.la/1386683).

10.1

1

1.0

`locationbar`

1

12

1

No

15

3

1

18

4

14

1

1.0

`matchMedia`

9

12

6

10

12.1

5.1

≤37

18

6

12.1

5

1.0

`maximize`

No

No

No

No

?

No

No

No

No

?

No

No

`menubar`

1

12

1

No

15

3

1

18

4

14

1

1.0

`message_event`

60

≤79

?

?

47

?

60

60

?

47

?

8.0

`messageerror_event`

60

≤79

57

?

47

?

60

60

57

47

?

8.0

`minimize`

No

No

No

No

?

No

No

No

No

?

No

No

`moveBy`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`moveTo`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`mozAnimationStartTime`

No

No

4-42

No

No

No

No

No

4-42

No

No

No

`mozInnerScreenX`

No

No

3.6

No

No

No

No

No

4

No

No

No

`mozInnerScreenY`

No

No

3.6

No

No

No

No

No

4

No

No

No

`mozPaintCount`

No

No

4-72

No

No

No

No

No

4-79

No

No

No

`name`

1

12

1

Before Firefox 86, if a new page from another domain is loaded into a tab, then `window.name` is not set to an empty string, which can allow some cross-site attacks. See [bug 1685089](https://bugzil.la/1685089) and [bug 444222](https://bugzil.la/444222).

4

≤12.1

1

1

18

4

Before Firefox 86, if a new page from another domain is loaded into a tab, then `window.name` is not set to an empty string, which can allow some cross-site attacks. See [bug 1685089](https://bugzil.la/1685089) and [bug 444222](https://bugzil.la/444222).

≤12.1

1

1.0

`navigator`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`offline_event`

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

`onappinstalled`

64

≤79

49-76

No

No

No

57

57

49

No

No

7.0

`onbeforeinstallprompt`

Yes

≤79

No

No

Yes

No

Yes

Yes

No

Yes

No

Yes

`ondevicelight`

No

13-79

15

No

No

No

No

No

15

No

No

No

`ondevicemotion`

31

12

9

11

18

No

4.4

31

9

18

No

2.0

`ondeviceorientation`

7

12

9

11

15

No

≤37

18

9

14

No

1.0

`ondeviceorientationabsolute`

50

79

No

No

37

No

50

50

No

37

No

5.0

`ondeviceproximity`

No

No

15

No

No

No

No

No

15

No

No

No

`ongamepadconnected`

35

21-35

≤18

29

No

22

15-22

10.1

No

35

25-35

32

22

14-22

No

3.0

1.5-3.0

`ongamepaddisconnected`

35

21-35

≤18

29

No

22

15-22

10.1

No

35

25-35

32

22

14-22

No

3.0

1.5-3.0

`online_event`

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

`onorientationchange`

No

No

No

No

No

No

Yes

Yes

Yes

Yes

Yes

Yes

`onpaint`

No

No

No

No

?

No

No

No

No

?

No

No

`onuserproximity`

No

No

15

No

No

No

No

No

15

No

No

No

`onvrdisplayactivate`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

No

55

No

No

No

`onvrdisplayblur`

No

15-79

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

`onvrdisplayconnect`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

Yes

\["Chrome for Android 56 supports only Google Daydream View.", "Chrome for Android 57 adds support for Google Cardboard."\]

55

No

No

Yes

Supported on Samsung Internet for GearVR.

`onvrdisplaydeactivate`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

No

55

No

No

No

`onvrdisplaydisconnect`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

56

\["Chrome for Android 56 supports only Google Daydream View.", "Chrome for Android 57 adds support for Google Cardboard."\]

55

No

No

6.0

Supported on Samsung Internet for GearVR.

`onvrdisplayfocus`

No

15-79

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

`onvrdisplaypointerrestricted`

No

15-79

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

`onvrdisplaypointerunrestricted`

No

15-79

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

`onvrdisplaypresentchange`

65-80

15

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

56-80

\["Chrome for Android 56 supports only Google Daydream View.", "Chrome for Android 57 adds support for Google Cardboard."\]

55

No

No

6.0

Supported on Samsung Internet for GearVR.

`open`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`openDialog`

No

No

1-32

No

?

No

No

No

4-32

?

No

No

`opener`

1

12

1

9

3

1

1

18

4

10.1

1

1.0

`orientation`

No

No

No

No

No

No

Yes

Yes

Yes

Yes

Yes

Yes

`orientationchange_event`

No

No

No

No

No

No

Yes

Yes

44

Yes

Yes

Yes

`originAgentCluster`

88

90

No

No

No

No

90

88

No

No

No

No

`outerHeight`

1

12

1

9

9

3

Yes

Yes

4

10.1

3

Yes

`outerWidth`

1

12

1

9

9

3

Yes

Yes

4

10.1

3

Yes

`pagehide_event`

3

12

Yes

Yes

Yes

Yes

≤37

18

Yes

Yes

Yes

1.0

`pageshow_event`

3

12

Yes

Yes

Yes

Yes

≤37

18

Yes

Yes

Yes

1.0

`pageXOffset`

1

12

1

9

3

1

1

18

4

10.1

1

1.0

`pageYOffset`

1

12

1

9

3

1

1

18

4

10.1

1

1.0

`parent`

1

12

1

9

3

1.3

1

18

4

10.1

1

1.0

`paste_event`

1

12

Yes

11

15

Yes

1

18

Yes

14

?

1.0

`performance`

6

12

7

9

15

8

Yes

Yes

7

14

9

Yes

`personalbar`

1

12

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`pkcs11`

No

No

1-29

No

?

No

No

No

4-29

?

No

No

`popstate_event`

5

Before version 34, Chrome would fire a `popstate` event on page load.

12

4

Firefox emits a `popstate` event on page load.

10

11.5

6

Before version 10, Safari would fire a `popstate` event on page load.

≤37

Before version 37, WebView would fire a `popstate` event on page load.

18

Before version 34, Chrome would fire a `popstate` event on page load.

4

Firefox emits a `popstate` event on page load.

11.5

5.1

Before version 10, Safari would fire a `popstate` event on page load.

1.0

Before version 2.0, Samsung Internet would fire a `popstate` event on page load.

`postMessage`

1

12

8

Supports sending `File` and `FileList` objects between windows. This is only allowed if the recipient's principal is contained within the sender's principal for security reasons.

6

The `message` parameter is serialized using the [structured clone algorithm](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Structured_clone_algorithm). This means you can pass a broad variety of data objects safely to the destination window without having to serialize them yourself.

3-6

The `message` parameter must be a string.

10

IE10 had an important limitation: see this [article](https://stackoverflow.com/questions/16226924/is-cross-origin-postmessage-broken-in-ie10) for details.

8-10

Support only for `<frame>` and `<iframe>`.

9.5

4

1

18

8

Supports sending `File` and `FileList` objects between windows. This is only allowed if the recipient's principal is contained within the sender's principal for security reasons.

6

The `message` parameter is serialized using the [structured clone algorithm](https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Structured_clone_algorithm). This means you can pass a broad variety of data objects safely to the destination window without having to serialize them yourself.

4-6

The `message` parameter must be a string.

10.1

3.2

1.0

`print`

1

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

12

1

5

6

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1.1

1

Starting with WebView 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

18

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

No

See [bug 1247609](https://bugzil.la/1247609).

10.1

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1

1.0

Starting with Samsung Internet 5.0, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

`prompt`

1

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

12

1

4

This function has no effect in the Modern UI/Metro version of Internet Explorer for Windows 8. It does not display a prompt to the user, and always returns `undefined`. It is not clear whether this is a bug or intended behavior. Desktop versions of IE do implement this function.

3

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1

1

Starting with WebView 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

18

Starting with Chrome 46, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

4

10.1

Starting with Opera 33, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

1

1.0

Starting with Samsung Internet 5.0, this method is blocked inside an `<iframe>` unless its sandbox attribute has the value `allow-modals`.

`rejectionhandled_event`

49

≤79

69

68

No

36

11

49

49

68

36

11.3

5.0

`releaseEvents`

1

12

1

11

≤12.1

1

1

18

4

≤12.1

1

1.0

`requestAnimationFrame`

24

10

12

23

Callback parameter is a `DOMHighResTimestamp`. This means ten microsecond precision and zero time as `performance.now()`.

11-42

Callback parameter is a `DOMTimestamp`. This means millisecond precision and zero time as `Date.now()`.

4-11

Could be called with no input parameters.

10

15

15

6.1

6

≤37

≤37

25

18

23

14-42

14

14

7

6.1

1.5

1.0

`requestFileSystem`

13

≤18

No

No

No

No

37

Yes

No

No

No

Yes

`requestIdleCallback`

47

79

55

No

34

No

47

47

55

34

No

5.0

`resize_event`

1

Chrome does not emit a `resize` event on page load.

12

Prior to Edge 79, Edge emitted a `resize` event on page load. This is no longer the case.

1

Prior to Firefox 68, Firefox emitted a `resize` event on page load. This is no longer the case.

4

7

Opera does not emit a `resize` event on page load.

1.1

1

Webview does not emit a `resize` event on page load.

18

Chrome does not emit a `resize` event on page load.

4

Prior to Firefox 68, Firefox emitted a `resize` event on page load. This is no longer the case.

10.1

Opera does not emit a `resize` event on page load.

1

1.0

Samsung Internet does not emit a `resize` event on page load.

`resizeBy`

1

12

1

Since Firefox 7, it's no longer possible for a web site to change the default size of a window in a browser if the window wasn't created by `window.open` or contains more than one tab. [See here](https://bugzil.la/565541#c24) for more details.

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`resizeTo`

1

12

1

Since Firefox 7, it's no longer possible for a web site to change the default size of a window in a browser if the window wasn't created by `window.open` or contains more than one tab. [See here](https://bugzil.la/565541#c24) for more details.

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`resolveLocalFileSystemURL`

13

≤79

No

No

No

No

Yes

Yes

No

No

No

Yes

`returnValue`

No

No

No

No

?

No

No

No

No

?

No

No

`routeEvent`

No

No

1-25

No

No

No

No

No

4-25

No

No

No

`screen`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`screenLeft`

1

12

64

5

≤12.1

1

1

18

64

≤12.1

1

1.0

`screenTop`

1

12

64

5

≤12.1

1

1

18

64

≤12.1

1

1.0

`screenX`

1

12

1

Before Firefox 28, Gecko was using device pixels instead of CSS pixels; in other words, it was assuming a value of `screenPixelsPerCSSPixel` of 1 for any device.

9

≤12.1

1

1

18

4

Before Firefox 28, Gecko was using device pixels instead of CSS pixels; in other words, it was assuming a value of `screenPixelsPerCSSPixel` of 1 for any device.

≤12.1

1

1.0

`screenY`

1

12

1

Before Firefox 28, Gecko was using device pixels instead of CSS pixels; in other words, it was assuming a value of `screenPixelsPerCSSPixel` of 1 for any device.

9

≤12.1

1

1

18

4

Before Firefox 28, Gecko was using device pixels instead of CSS pixels; in other words, it was assuming a value of `screenPixelsPerCSSPixel` of 1 for any device.

≤12.1

1

1.0

`scroll`

1

12

1

4

3

1

1

18

4

10.1

1

1.0

`scrollbars`

1

12

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`scrollBy`

1

79

12-79

Only `scrollBy(x-coord, y-coord)` is supported.

1

11

Only `scrollBy(x-coord, y-coord)` is supported.

3

1

1

18

4

10.1

1

1.0

`scrollByLines`

No

No

1

No

?

No

No

No

4

?

No

No

`scrollByPages`

No

No

1

No

?

No

No

No

4

?

No

No

`scrollMaxX`

No

No

1

No

?

No

No

No

4

?

No

No

`scrollMaxY`

No

No

1

No

?

No

No

No

4

?

No

No

`scrollTo`

1

12

1

4

4

1

1

18

4

10.1

1

1.0

`scrollX`

1

1

12

12

1

1

9

9.6

4

1

1

1

1

18

18

4

4

10.1

10.1

1

1

1.0

1.0

`scrollY`

1

1

12

12

1

1

9

9.6

4

1

1

1

1

18

18

4

4

10.1

10.1

1

1

1.0

1.0

`self`

1

12

1

4

≤12.1

3

1

18

4

≤12.1

1

1.0

`sessionStorage`

5

12

2

8

10.5

4

≤37

18

4

11

3.2

1.0

`setCursor`

No

No

No

No

?

No

No

No

No

?

No

No

`setImmediate`

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

`setResizable`

No

No

1

No

?

No

No

No

4

?

No

No

`showDirectoryPicker`

86

86

No

No

72

No

No

No

No

No

No

No

`showModalDialog`

Yes-43

No

3-56

4

No

5.1

See [WebKit bug 151885](https://webkit.org/b/151885) for possible future removal from Safari.

No

No

No

No

No

No

`showOpenFilePicker`

86

86

No

No

72

No

No

No

No

No

No

No

`showSaveFilePicker`

86

86

No

No

72

No

No

No

No

No

No

No

`sidebar`

No

No

1

From Firefox 78 `AddSearchProvider()` does nothing, as the specification requires.

No

?

No

No

No

4

?

No

No

`sizeToContent`

No

No

1

No

?

No

No

No

4

This method has no effect as a page is always in a tab.

?

No

No

`speechSynthesis`

33

14

49

No

Yes

7

No

See [bug 487255](https://crbug.com/487255)

Yes

No

No

7

Yes

`status`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`statusbar`

1

12

1

No

15

3

1

18

4

14

1

1.0

`stop`

1

14

1

No

≤12.1

3

1

18

4

≤12.1

1

1.0

`storage_event`

1

≤18

45

?

15

?

≤37

18

45

14

?

1.0

`styleMedia`

6

12

No

9

15

5

≤37

18

No

14

4

1.0

`toolbar`

1

12

1

No

15

3

1

18

4

14

1

1.0

`top`

1

12

1

Starting in Firefox 6, this property is read only, as defined by the standard.

4

≤12.1

3

1

18

4

≤12.1

1

1.0

`transitioncancel_event`

No

No

53

?

?

13.1

12

No

No

53

?

13.4

12

No

`transitionend_event`

No

No

51

?

?

Yes

No

No

51

?

Yes

No

`transitionrun_event`

No

No

53

?

?

13.1

12

No

No

53

?

13.4

12

No

`transitionstart_event`

No

No

53

?

?

13.1

12

No

No

53

?

13.4

12

No

`trustedTypes`

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

`unhandledrejection_event`

49

79

69

68

No

36

11

49

49

68

36

11.3

5.0

`unload_event`

1

12

1

4

4

3

1

18

4

10.1

1

1.0

`updateCommands`

No

No

1

No

?

No

No

No

4

?

No

No

`visualViewport`

61

79

63

No

48

13

61

61

63

45

13

8.0

`vrdisplayactivate_event`

No

No

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

No

55

No

No

No

`vrdisplayblur_event`

No

15-79

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

`vrdisplayconnect_event`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

Yes

\["Chrome for Android 56 supports only Google Daydream View.", "Chrome for Android 57 adds support for Google Cardboard."\]

55

No

No

Yes

Supported on Samsung Internet for GearVR.

`vrdisplaydeactivate_event`

No

No

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

No

55

No

No

No

`vrdisplaydisconnect_event`

No

15-79

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

56

\["Chrome for Android 56 supports only Google Daydream View.", "Chrome for Android 57 adds support for Google Cardboard."\]

55

No

No

6.0

Supported on Samsung Internet for GearVR.

`vrdisplayfocus_event`

No

15-79

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

`vrdisplaypointerrestricted_event`

No

15-79

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

`vrdisplaypointerunrestricted_event`

No

15-79

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

`vrdisplaypresentchange_event`

65

15

55

Windows support was enabled in Firefox 55.

64

macOS support was enabled in Firefox 64.

No

No

No

No

56

\["Chrome for Android 56 supports only Google Daydream View.", "Chrome for Android 57 adds support for Google Cardboard."\]

55

No

No

6.0

Supported on Samsung Internet for GearVR.

`window`

1

12

1

4

≤12.1

3

1

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window</a>
