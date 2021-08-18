&lt;input type="image"&gt;
==========================

[`<input>`](../input) elements of type `image` are used to create graphical submit buttons, i.e. submit buttons that take the form of an image rather than text.

<table><tbody><tr class="odd"><td><strong><a href="#value">Value</a></strong></td><td>None — the <code>value</code> attribute should not be specified.</td></tr><tr class="even"><td><strong>Events</strong></td><td>None.</td></tr><tr class="odd"><td><strong>Supported common attributes</strong></td><td><a href="../input#attr-alt"><code>alt</code></a>, <a href="../input#attr-src"><code>src</code></a>, <a href="../input#attr-width"><code>width</code></a>, <a href="../input#attr-height"><code>height</code></a>, <a href="../input#attr-formaction"><code>formaction</code></a>, <a href="../input#attr-formenctype"><code>formenctype</code></a>, <a href="../input#attr-formmethod"><code>formmethod</code></a>, <a href="../input#attr-formnovalidate"><code>formnovalidate</code></a>, <a href="../input#attr-formtarget"><code>formtarget</code></a></td></tr><tr class="even"><td><strong>IDL attributes</strong></td><td>None.</td></tr><tr class="odd"><td><strong>Methods</strong></td><td>None.</td></tr></tbody></table>

Value
-----

`<input type="image">` elements do not accept `value` attributes. The path to the image to be displayed is specified in the `src` attribute.

Additional attributes
---------------------

In addition to the attributes shared by all [`<input>`](../input) elements, `image` button inputs support the following attributes:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>alt</code></td><td>Alternate string to display when the image can't be shown</td></tr><tr class="even"><td><code>formaction</code></td><td>The URL to which to submit the data</td></tr><tr class="odd"><td><code>formenctype</code></td><td>The encoding method to use when submitting the form data</td></tr><tr class="even"><td><code>formmethod</code></td><td>The HTTP method to use when submitting the form</td></tr><tr class="odd"><td><code>formnovalidate</code></td><td>A Boolean which, if present, indicates that the form shouldn't be validated before submission</td></tr><tr class="even"><td><code>formtarget</code></td><td>A string indicating a browsing context from where to load the results of submitting the form</td></tr><tr class="odd"><td><code>height</code></td><td>The height, in CSS pixels, at which to draw the image</td></tr><tr class="even"><td><code>src</code></td><td>The URL from which to load the image</td></tr><tr class="odd"><td><code>width</code></td><td>The width, in CSS pixels, at which to draw the image</td></tr></tbody></table>

### `alt`

The `alt` attribute provides an alternate string to use as the button's label if the image cannot be shown (due to error, a [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) that cannot or is configured not to show images, or if the user is using a screen reading device). If provided, it must be a non-empty string appropriate as a label for the button.

For example, if you have a graphical button that shows an image with an icon and/or image text "Login Now", you should also set the `alt` attribute to something like `Login Now`.

**Important:** While the `alt` attribute is technically optional, you should always include one to maximize the usability of your content.

Functionally, the `<input type="image">` `alt` attribute works just like the `alt` attribute on [`<img>`](../img) elements.

### `formaction`

A string indicating the URL to which to submit the data. This takes precedence over the [`action`](../form#attr-action) attribute on the [`<form>`](../form) element that owns the [`<input>`](../input).

This attribute is also available on `<input type="submit">` and [`<button>`](../button) elements.

### `formenctype`

A string that identifies the encoding method to use when submitting the form data to the server. There are three permitted values:

`application/x-www-form-urlencoded`  
This, the default value, sends the form data as a string after URL encoding the text using an algorithm such as [`encodeURI()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/encodeURI).

`multipart/form-data`  
Uses the [`FormData`](https://developer.mozilla.org/en-US/docs/Web/API/FormData) API to manage the data, allowing for files to be submitted to the server. You *must* use this encoding type if your form includes any [`<input>`](../input) elements of [`type`](../input#attr-type) `file` (`<input type="file">`).

`text/plain`  
Plain text; mostly useful only for debugging, so you can easily see the data that's to be submitted.

If specified, the value of the `formenctype` attribute overrides the owning form's [`action`](../form#attr-action) attribute.

This attribute is also available on `<input type="submit">` and [`<button>`](../button) elements.

### `formmethod`

A string indicating the HTTP method to use when submitting the form's data; this value overrides any [`method`](../form#attr-method) attribute given on the owning form. Permitted values are:

`get`  
A URL is constructed by starting with the URL given by the `formaction` or [`action`](../form#attr-action) attribute, appending a question mark ("?") character, then appending the form's data, encoded as described by `formenctype` or the form's [`enctype`](../form#attr-enctype) attribute. This URL is then sent to the server using an HTTP [`get`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) request. This method works well for simple forms that contain only ASCII characters and have no side effects. This is the default value.

`post`  
The form's data is included in the body of the request that is sent to the URL given by the `formaction` or [`action`](../form#attr-action) attribute using an HTTP [`post`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) request. This method supports complex data and file attachments.

`dialog`  
This method is used to indicate that the button closes the dialog with which the input is associated, and does not transmit the form data at all.

This attribute is also available on `<input type="submit">` and [`<button>`](../button) elements.

### `formnovalidate`

A Boolean attribute which, if present, specifies that the form should not be validated before submission to the server. This overrides the value of the [`novalidate`](../form#attr-novalidate) attribute on the element's owning form.

This attribute is also available on `<input type="submit">` and [`<button>`](../button) elements.

### `formtarget`

A string which specifies a name or keyword that indicates where to display the response received after submitting the form. The string must be the name of a **browsing context** (that is, a tab, window, or [`<iframe>`](../iframe). A value specified here overrides any target given by the [`target`](../form#attr-target) attribute on the [`<form>`](../form) that owns this input.

In addition to the actual names of tabs, windows, or inline frames, there are a few special keywords that can be used:

`_self`  
Loads the response into the same browsing context as the one that contains the form. This will replace the current document with the received data. This is the default value used if none is specified.

`_blank`  
Loads the response into a new, unnamed, browsing context. This is typically a new tab in the same window as the current document, but may differ depending on the configuration of the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent).

`_parent`  
Loads the response into the parent browsing context of the current one. If there is no parent context, this behaves the same as `_self`.

`_top`  
Loads the response into the top-level browsing context; this is the browsing context that is the topmost ancestor of the current context. If the current context is the topmost context, this behaves the same as `_self`.

This attribute is also available on `<input type="submit">` and [`<button>`](../button) elements.

### `height`

A number specifying the height, in CSS pixels, at which to draw the image specified by the `src` attribute.

### `src`

A string specifying the URL of the image file to display to represent the graphical submit button. When the user interacts with the image, the input is handled like any other button input.

### `width`

A number indicating the width at which to draw the image, in CSS pixels.

Obsolete attributes
-------------------

The following attribute was defined by HTML 4 for `image` inputs, but was not implemented by all browsers and has since been deprecated:

<table><thead><tr class="header"><th>Attribute</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>usemap</code></td><td>The name of an image map (<a href="../map"><code>&lt;map&gt;</code></a>) element to use with the image; this is obsolete. Use the <a href="../img"><code>&lt;img&gt;</code></a> element to create image maps instead</td></tr></tbody></table>

### `usemap`

If `usemap` is specified, it must be the name of an image map element, [`<map>`](../map), that defines an image map to use with the image. This usage is obsolete; you should switch to using the [`<img>`](../img) element when you want to use image maps.

Using image inputs
------------------

The `<input type="image">` element is a [replaced element](https://developer.mozilla.org/en-US/docs/Web/CSS/Replaced_element) (an element whose content isn't generated or directly managed by the CSS layer), behaving in much the same way as a regular [`<img>`](../img) element, but with the capabilities of a [submit button](submit).

### Essential image input features

Let's look at a basic example that includes all the essential features you'd need to use (These work exactly the same as they do on the `<img>` element.):

    <input id="image" type="image" width="100" height="30" alt="Login"
           src="https://raw.githubusercontent.com/mdn/learning-area/master/html/forms/image-type-example/login.png">

-   The [`src`](../input#attr-src) attribute is used to specify the path to the image you want to display in the button.
-   The [`alt`](../input#attr-alt) attribute provides alt text for the image, so screen reader users can get a better idea of what the button is used for. It will also display if the image can't be shown for any reason (for example if the path is misspelled). If possible, use text which matches the label you'd use if you were using a standard submit button.
-   The [`width`](../input#attr-width) and [`height`](../input#attr-height) attributes are used to specify the width and height the image should be shown at, in pixels. The button is the same size as the image; if you need the button's hit area to be bigger than the image, you will need to use CSS (e.g. [`padding`](https://developer.mozilla.org/en-US/docs/Web/CSS/padding)). Also, if you specify only one dimension, the other is automatically adjusted so that the image maintains its original aspect ratio.

### Overriding default form behaviors

`<input type="image">` elements — like regular [submit buttons](submit) — can accept a number of attributes that override the default form behavior:

`formaction`  
The URI of a program that processes the information submitted by the input element; overrides the [`action`](../form#attr-action) attribute of the element's form owner.

`formenctype`  
Specifies the type of content that is used to submit the form to the server. Possible values are:

-   `application/x-www-form-urlencoded`: The default value if the attribute is not specified.
-   `text/plain`.

If this attribute is specified, it overrides the [`enctype`](../form#attr-enctype) attribute of the element's form owner.

`formmethod`  
Specifies the HTTP method that the browser uses to submit the form. Possible values are:

-   `post`: The data from the form is included in the body of the form and is sent to the server.
-   `get`: The data from the form is appended to the `form` attribute URI, with a '?' as a separator, and the resulting URI is sent to the server. Use this method when the form has no side-effects and contains only ASCII characters.

If specified, this attribute overrides the [`method`](../form#attr-method) attribute of the element's form owner.

`formnovalidate`  
A Boolean attribute specifying that the form is not to be validated when it is submitted. If this attribute is specified, it overrides the [`novalidate`](../form#attr-novalidate) attribute of the element's form owner.

`formtarget`  
A name or keyword indicating where to display the response that is received after submitting the form. This is a name of, or keyword for, a *browsing context* (for example, tab, window, or inline frame). If this attribute is specified, it overrides the [`target`](../form#attr-target) attribute of the element's form owner. The following keywords have special meanings:

-   \_`self`: Load the response into the same browsing context as the current one. This value is the default if the attribute is not specified.
-   `_blank`: Load the response into a new unnamed browsing context.
-   `_parent`: Load the response into the parent browsing context of the current one. If there is no parent, this option behaves the same way as `_self`.
-   `_top`: Load the response into the top-level browsing context (that is, the browsing context that is an ancestor of the current one, and has no parent). If there is no parent, this option behaves the same as `_self`.

### Using the x and y data points

When you submit a form using a button created with `<input type="image">`, two extra data points are submitted to the server automatically by the browser — `x` and `y`. You can see this in action in our [X Y coordinates example](https://mdn.github.io/learning-area/html/forms/image-type-example/xy-coordinates-example.html).

When you click on the image to submit the form, you'll see the data appended to the URL as parameters, for example `?x=52&y=55`. If the image input has a [`name`](../input#attr-name) attribute, then keep in mind that the specified name is prefixed on every attribute, so if the `name` is `position`, then the returned coordinates would be formatted in the URL as `?position.x=52&position.y=55`. This, of course, applies to all other attributes as well.

These are the X and Y coordinates of the image that the mouse clicked on to submit the form, where (0,0) is the top-left of the image. These can be used when the position the image was clicked on is significant, for example you might have a map that when clicked, sends the coordinates that were clicked to the server. The server-side code then works out what location was clicked on, and returns information about places nearby.

In our above example, we could write server-side code that works out what color was clicked on by the coordinates submitted, and keeps a tally of the favorite colors people voted for.

### Adjusting the image's position and scaling algorithm

You can use the [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position) property to adjust the positioning of the image within the `<input>` element's frame, and the [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit) property to control how the image's size is adjusted to fit within the frame. This allows you to specify a frame for the image using the `width` and `height` attributes to set aside space in the layout, then adjust where within that space the image is located and how (or if) it is scaled to occupy that space.

Examples
--------

### A login form

The following example shows the same button as before, but included in the context of a typical login form.

#### HTML

    <form>
      <p>Login to your account</p>
      <div>
        <label for="userId">User ID</label>
        <input type="text" id="userId" name="userId">
      </div>
      <div>
        <label for="pwd">Password</label>
        <input type="password" id="pwd" name="pwd">
      </div>
      <div>
        <input id="image" type="image" src="https://raw.githubusercontent.com/mdn/learning-area/master/html/forms/image-type-example/login.png" alt="Login" width="100">
      </div>
    </form>

#### CSS

And now some simple CSS to make the basic elements sit more neatly:

    div {
      margin-bottom: 10px;
    }

    label {
      display: inline-block;
      width: 70px;
      text-align: right;
      padding-right: 10px;
    }

### Adjusting the image position and scaling

In this example, we adapt the previous example to set aside more space for the image and then adjust the actual image's size and positioning using [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit) and [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position).

#### HTML

    <form>
      <p>Login to your account</p>
      <div>
        <label for="userId">User ID</label>
        <input type="text" id="userId" name="userId">
      </div>
      <div>
        <label for="pwd">Password</label>
        <input type="password" id="pwd" name="pwd">
      </div>
      <div>
        <input id="image" type="image"
          src="https://raw.githubusercontent.com/mdn/learning-area/master/html/forms/image-type-example/login.png"
          alt="Login" width="200" height="100">
      </div>
    </form>

#### CSS

    div {
      margin-bottom: 10px;
    }

    label {
      display: inline-block;
      width: 70px;
      text-align: right;
      padding-right: 10px;
    }

    #image {
      object-position: right top;
      object-fit: contain;
      background-color: #ddd;
    }

Here, `object-position` is configured to draw the image at the top-right corner of the element, while `object-fit` is set to `contain`, which indicates that the image should be drawn at the largest size that will fit within the element's box without altering its aspect ratio. Note the visible grey background of the element still visible in the area not covered by the image.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comments</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/forms.html#image-button-state-(type=image)">HTML Living Standard<br />
<span class="small">The definition of '&lt;input type="image"&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/forms.html#image-button-state-%28type=image%29">HTML5<br />
<span class="small">The definition of '&lt;input type="image"&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`image`

Yes

12

Yes

Yes

Yes

Yes

Yes

?

Yes

Yes

Yes

?

See also
--------

-   [`<input>`](../input) and the [`HTMLInputElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement) interface which implements it.
-   Positioning and sizing the image within the `<input>` element's frame: [`object-position`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-position) and [`object-fit`](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit)
-   [Compatibility of CSS properties](https://developer.mozilla.org/en-US/docs/Learn/Forms/Property_compatibility_table_for_form_controls)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/image" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/image</a>
