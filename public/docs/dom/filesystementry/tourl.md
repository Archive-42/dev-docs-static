# FileSystemEntry.toURL()

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The [`FileSystemEntry`](../filesystementry) interface's method ` toURL``() ` creates and returns a string containing a URL which can be used to identify the file system entry. This is done by exposing a new URL scheme—`filesystem:`—that can be used as the value of `src` and `href` attributes.

## Syntax

    FileSystemEntry.toURL([mimeType]);

### Parameters

`mimeType` <span class="badge inline optional">Optional</span>  
An optional string specifying the MIME type to use when interpreting the file. This can be used to help deal with files whose types aren't recognized automatically by the user agent. If this parameter is omitted, the user agent uses its standard algorithms to identify the file.

### Return value

A [`DOMString`](../domstring) containing a URL that can then be used as a document reference in HTML content, or an empty string if the URL can't be generated (such as if the file system implementation doesn't support `toURL()`).

## Example

If you have a [`FileSystemFileEntry`](../filesystemfileentry) corresponding to an image file in a file system available to your Web site or app, you can call `toURL()` to get its URL for use in HTML. If your site is located at `http://my-awesome-website.woot`, and you have a temporary file system that contains an image file named `awesomesauce.jpg`, the URL returned by `toURL()` might be (depending on the browser's implementation) something like `"filesystem:http://my-awesome-website.woot/temporary/awesomesauce.jpg"`.

Code that makes use of this might look like this:

    let img = document.createElement("img");

    img.src = imageFileEntry.toURL();
    document.body.appendChild(img);

Assuming the scenario mentioned before the code, the result would be HTML that looks like this being appended to the end of the document:

    <img src="filesystem:http://my-awesome-website.woot/temporary/awesomesauce.jpg">

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

`toURL`

8

79

No

No

No

No

≤37

18

No

No

No

1.0

## See also

- [File and Directory Entries API](../file_and_directory_entries_api)
- [Introduction to the File System API](../file_and_directory_entries_api/introduction)
- [`FileSystemDirectoryEntry.removeRecursively()`](../filesystemdirectoryentry/removerecursively)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/toURL" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/FileSystemEntry/toURL</a>
