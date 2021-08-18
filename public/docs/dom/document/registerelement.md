# Document.registerElement()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Warning:** `document.registerElement()` is deprecated in favor of [`customElements.define()`](../customelementregistry/define).

**Draft**

This page is not complete.

The `document.registerElement()` method registers a new [custom element](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements) in the browser and returns a constructor for the new element.

**Note:** This is an experimental technology. The browser you use it in must support Web Components. See [Enabling Web Components in Firefox](https://developer.mozilla.org/en-US/docs/Web/Web_Components#enabling_web_components_in_firefox).

## Syntax

    var constructor = document.registerElement(tag-name, options);

### Parameters

_tag-name_  
The name of the custom element. The name must contain a dash (-), for example `my-tag`.

_options<span class="badge inline optional">Optional</span>_  
An object with properties **prototype** to base the custom element on, and **extends**, an existing tag to extend. Both of these are optional.

## Example

Here is a very simple example:

    var Mytag = document.registerElement('my-tag');

Now the new tag is registered in the browser. The `Mytag` variable holds a constructor that you can use to create a `my-tag` element in the document as follows:

    document.body.appendChild(new Mytag());

This inserts an empty `my-tag` element that will be visible if you use the browser's developer tools. It will not be visible if you use the browser's view source capability. And it won't be visible in the browser unless you add some content to the tag. Here is one way to add content to the new tag:

    var mytag = document.getElementsByTagName("my-tag")[0];
    mytag.textContent = "I am a my-tag element.";

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

`registerElement`

33-80

79-80

31-59

No

23-67

No

4.4.3-80

33-80

31-59

24-57

No

3.0-13.0

## See also

- [Custom Elements](https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/registerElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document/registerElement</a>
