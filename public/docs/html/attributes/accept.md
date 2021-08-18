HTML attribute: accept
======================

The `accept` attribute takes as its value a comma-separated list of one or more file types, or [unique file type specifiers](#unique_file_type_specifiers), describing which file types to allow. The accept property is an attribute of the [file](../element/input/file) [`<input>`](../element/input) type. It was supported on the [`<form>`](../element/form) element, but was removed in favor of [file](../element/input/file) in HTML5.

Because a given file type may be identified in more than one manner, it's useful to provide a thorough set of type specifiers when you need files of specific type, or use the wild card to denote a type of any format is acceptable.

For instance, there are a number of ways Microsoft Word files can be identified, so a site that accepts Word files might use an `<input>` like this:

    <input type="file" id="docpicker"
      accept=".doc,.docx,application/msword,application/vnd.openxmlformats-officedocument.wordprocessingml.document">

Whereas if you're accepting a media file, you may want to be include any format of that media type:

    <input type="file" id="soundFile" accept="audio/*">
    <input type="file" id="videoFile" accept="video/*">
    <input type="file" id="imageFile" accept="image/*">

The `accept` attribute doesn't validate the types of the selected files; it provides hints for browsers to guide users towards selecting the correct file types. It is still possible (in most cases) for users to toggle an option in the file chooser that makes it possible to override this and select any file they wish, and then choose incorrect file types.

Because of this, you should make sure that expected requirement is validated server-side.

Examples
--------

When set on a file input type, the native file picker that opens up should only enable selecting files of the correct file type. Most operating systems lighten the files that don't match the criteria and aren't selectable.

    <p>
        <label for="soundFile">Select an audio file:</label>
        <input type="file" id="soundFile" accept="audio/*">
        </p>
        <p>
        <label for="videoFile">Select a video file:</label>
        <input type="file" id="videoFile" accept="video/*">
        </p>
        <p>
        <label for="imageFile">Select some images:</label>
        <input type="file" id="imageFile" accept="image/*" multiple>
        </p>

Note the last example allows you to select multiple images. See the `multiple` attribute for more information.

Unique file type specifiers
---------------------------

A **unique file type specifier** is a string that describes a type of file that may be selected by the user in an [`<input>`](../element/input) element of type `file`. Each unique file type specifier may take one of the following forms:

-   A valid case-insensitive filename extension, starting with a period (".") character. For example: `.jpg`, `.pdf`, or `.doc`.
-   A valid MIME type string, with no extensions.
-   The string `audio/*` meaning "any audio file".
-   The string `video/*` meaning "any video file".
-   The string `image/*` meaning "any image file".

The `accept` attribute takes as its value a string containing one or more of these unique file type specifiers, separated by commas. For example, a file picker that needs content that can be presented as an image, including both standard image formats and PDF files, might look like this:

    <input type="file" accept="image/*,.pdf">

Using file inputs
-----------------

### A basic example

    <form method="post" enctype="multipart/form-data">
     <div>
       <label for="file">Choose file to upload</label>
       <input type="file" id="file" name="file" multiple>
     </div>
     <div>
       <button>Submit</button>
     </div>
    </form>

This produces the following output:

**Note**: You can find this example on GitHub too — see the [source code](https://github.com/mdn/learning-area/blob/master/html/forms/file-examples/simple-file.html), and also [see it running live](https://mdn.github.io/learning-area/html/forms/file-examples/simple-file.html).

Regardless of the user's device or operating system, the file input provides a button that opens up a file picker dialog that allows the user to choose a file.

Including the `multiple` attribute, as shown above, specifies that multiple files can be chosen at once. The user can choose multiple files from the file picker in any way that their chosen platform allows (e.g. by holding down Shift or Control, and then clicking). If you only want the user to choose a single file per `<input>`, omit the `multiple` attribute.

### Limiting accepted file types

Often you won't want the user to be able to pick any arbitrary type of file; instead, you often want them to select files of a specific type or types. For example, if your file input lets users upload a profile picture, you probably want them to select web-compatible image formats, such as [JPEG](https://developer.mozilla.org/en-US/docs/Glossary/jpeg) or [PNG](https://developer.mozilla.org/en-US/docs/Glossary/PNG).

Acceptable file types can be specified with the [`accept`](../element/input/file#attr-accept) attribute, which takes a comma-separated list of allowed file extensions or MIME types. Some examples:

-   `accept="image/png"` or `accept=".png"` — Accepts PNG files.
-   `accept="image/png, image/jpeg"` or `accept=".png, .jpg, .jpeg"` — Accept PNG or JPEG files.
-   `accept="image/*"` — Accept any file with an `image/*` MIME type. (Many mobile devices also let the user take a picture with the camera when this is used.)
-   `accept=".doc,.docx,.xml,application/msword,application/vnd.openxmlformats-officedocument.wordprocessingml.document"` — accept anything that smells like an MS Word document.

Let's look at a more complete example:

    <form method="post" enctype="multipart/form-data">
      <div>
        <label for="profile_pic">Choose file to upload</label>
        <input type="file" id="profile_pic" name="profile_pic"
              accept=".jpg, .jpeg, .png">
      </div>
      <div>
        <button>Submit</button>
      </div>
    </form>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/input.html#attr-input-accept">HTML Living Standard<br />
<span class="small">The definition of 'accept attribute' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/sec-forms.html#attr-input-accept">HTML 5.1<br />
<span class="small">The definition of 'accept attribute' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td></tr></tbody></table>

Browser compatibility
---------------------

No compatibility data found for `html.elements.attribute.accept`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

See also
--------

-   [Using files from web applications](https://developer.mozilla.org/en-US/docs/Web/API/File/Using_files_from_web_applications)
-   [File API](https://developer.mozilla.org/en-US/docs/Web/API/File)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/accept" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/accept</a>
