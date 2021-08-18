Window.window
=============

The `window` property of a [`Window`](../window) object points to the window object itself. Thus, the following expressions all return the same window object:

    window.window
    window.window.window
    window.window.window.window
    // ...

In web pages, the window object is also a *global object*. This means:

1.  global variables of your script are in fact properties of `window`:

        var global = {data: 0};
        alert(global === window.global); // displays "true"

2.  you can access built-in properties of the window object without having to type `window.` prefix:

        setTimeout("alert('Hi!')", 50); // equivalent to using window.setTimeout.
        alert(window === window.window); // displays "true"

The point of having the `window` property refer to the object itself, was likely to make it easy to refer to the global object. Otherwise, you'd have to do a manual `var window = this;` assignment at the top of your script.

Another reason, is that without this property you wouldn't be able to write, for example, "[`window.open('http://google.com/')`](open)". You'd have to use "open('http://google.com/')" instead.

Yet another reason to use this property, is for libraries which wish to offer OOP-versions, and non-OOP versions (especially JavaScript modules). For example, if we refer to "this.window.location.href", a [JavaScript module](https://developer.mozilla.org/en-US/docs/Mozilla/JavaScript_code_modules) could define a property called "window" inside of a class it defined (since no global "window" variable exists for it by default) which could be created after passing in a window object to the module class' constructor. Thus, "this.window" inside of its functions would refer to that window object. In the non-namespaced version, "this.window" would refer back to "window", and also be able to readily get the document location. Another advantage, is that the objects of such a class (even if the class were defined outside of a module) could change their reference to the window at will, they would not be able to do this if they had hard-coded a reference to "window". The default in the class could still be set as the current window object.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-window">HTML Living Standard<br />
<span class="small">The definition of 'Window.window' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No difference from the latest snapshot <a href="https://www.w3.org/TR/html51/">HTML 5.1</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/browsers.html#dom-window">HTML 5.1<br />
<span class="small">The definition of 'Window.window' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No difference from the <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/browsers.html#dom-window">HTML5<br />
<span class="small">The definition of 'Window.window' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>First snapshot containing the definition of <code>Window.window</code>.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/window" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/window</a>
