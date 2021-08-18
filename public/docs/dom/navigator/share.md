Navigator.share()
=================

**Secure context**

This feature is available only in [secure contexts](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) (HTTPS), in some or all [supporting browsers](#browser_compatibility).

The `navigator.share()` method of the Web Share API invokes the native sharing mechanism of the device.

Syntax
------

    const sharePromise = navigator.share(data);

### Parameters

`data`  
An object containing data to share. At least one of the following fields must be specified. Available options are:

-   `url`: A [`USVString`](../usvstring) representing a URL to be shared.
-   `text`: A [`USVString`](../usvstring) representing text to be shared.
-   `title`: A [`USVString`](../usvstring) representing the title to be shared.
-   `files`: A "FrozenArray" representing the array of files to be shared.

### Return value

A [`Promise`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) that will be fulfilled once a user has completed a share action (usually the user has chosen an application to share to). It will reject immediately if the data parameter is not correctly specified, and will also reject if the user cancels sharing.

Examples
--------

In our [Web share test](https://mdn.github.io/dom-examples/web-share/) ([see the source code](https://github.com/mdn/dom-examples/blob/master/web-share/index.html)) there is a button which, when clicked, invokes the Web Share API to share MDN's URL. The JavaScript looks like this:

    const shareData = {
      title: 'MDN',
      text: 'Learn web development on MDN!',
      url: 'https://developer.mozilla.org',
    }

    const btn = document.querySelector('button');
    const resultPara = document.querySelector('.result');

    // Must be triggered some kind of "user activation"
    btn.addEventListener('click', async () => {
      try {
        await navigator.share(shareData)
        resultPara.textContent = 'MDN shared successfully'
      } catch(err) {
        resultPara.textContent = 'Error: ' + err
      }
    });

#### **Sharing Files**

To share files, first test for and call `navigator.canShare()`. Then include an array of files in the call to `navigator.share():`

Notice: That the sample handles feature detection by testing for `navigator.canShare()` rather than for `navigator.share()`. The data object passed to `canShare()` only supports the `files` property. Image, video, audio, and text files can be shared.

    if (navigator.canShare && navigator.canShare({ files: filesArray })) {
      navigator.share({
        files: filesArray,
        title: 'Pictures',
        text: 'Our Pictures.',
      })
      .then(() => console.log('Share was successful.'))
      .catch((error) => console.log('Sharing failed', error));
    } else {
      console.log(`Your system doesn't support sharing files.`);
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/web-share/#share-method">Web Share API<br />
<span class="small">The definition of 'share()' in that specification.</span></a></td><td><span class="spec-draft">Draft</span></td><td></td></tr></tbody></table>

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

`share`

89

Not supported on macOS, see [bug 1144920](https://crbug.com/1144920).

81

No

No

No

12.1

No

61

79

Firefox for Android does not support sharing files or text.

48

12.2

8.0

See also
--------

-   [`navigator.canShare()`](canshare)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigator/share" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigator/share</a>
