# HTMLInputElement.multiple

The `HTMLInputElement.multiple` property indicates if an input can have more than one value. Firefox currently only supports `multiple` for `<input type="file">`.

## Example

    // fileInput is a <input type=file multiple>
    let fileInput = document.getElementById('myfileinput');

    if (fileInput.multiple == true) {

      for (let i = 0; i < fileInput.files.length; i++) {
        // Loop fileInput.files
      }

    // Only one file available
    } else {
      let file = fileInput.files.item(0);
    }

## See also

- [FileList](../filelist)
- [Bug 523771](https://bugzilla.mozilla.org/show_bug.cgi?id=523771) - Support &lt;input type=file multiple&gt;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#attr-input-multiple">HTML Living Standard<br />
<span class="small">The definition of 'multiple' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`multiple`

2

12

3.6

10

≤12.1

4

≤37

18

4

≤12.1

3.2

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/multiple" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLInputElement/multiple</a>
