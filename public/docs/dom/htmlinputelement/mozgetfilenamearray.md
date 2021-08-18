# HTMLInputElement.mozGetFileNameArray()

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `HTMLInputElement.mozGetFileNameArray()` method returns an array of the names of the files that were selected by the user on an HTML `input` element.

**Note:** This method is Gecko-specific and is not available in other browsers. Also, it throws an error if used in Web pages.

## Syntax

    inputElement.mozGetFileNameArray(aLength, aFileNames);

### Parameters

`aLength`  
If specified, will receive the number of file names in the returned array.

`aFileNames`  
Is an array into which the file names are placed.

## Example

    var numFiles = 0;
    var fileArray = {};

    inputElement.mozGetFileNameArray(numFiles, fileArray);

## Browser compatibility

No compatibility data found for `api.HTMLInputElement.mozGetFileNameArray`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
- [`HTMLInputElement`](../htmlinputelement)
- <span class="page-not-created">`Input.mozSetFileNameArray`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/mozGetFileNameArray" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/mozGetFileNameArray</a>
