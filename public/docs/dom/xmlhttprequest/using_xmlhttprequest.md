Using XMLHttpRequest
====================

In this guide, we'll take a look at how to use [`XMLHttpRequest`](../xmlhttprequest) to issue [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP) requests in order to exchange data between the web site and a server. Examples of both common and more obscure use cases for `XMLHttpRequest` are included.

To send an HTTP request, create an `XMLHttpRequest` object, open a URL, and send the request. After the transaction completes, the object will contain useful information such as the response body and the [HTTP status](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) of the result.

    function reqListener () {
      console.log(this.responseText);
    }

    var oReq = new XMLHttpRequest();
    oReq.addEventListener("load", reqListener);
    oReq.open("GET", "http://www.example.org/example.txt");
    oReq.send();

Types of requests
-----------------

A request made via `XMLHttpRequest` can fetch the data in one of two ways, asynchronously or synchronously. The type of request is dictated by the optional `async` argument (the third argument) that is set on the [`XMLHttpRequest.open()`](open) method. If this argument is `true` or not specified, the `XMLHttpRequest` is processed asynchronously, otherwise the process is handled synchronously. A detailed discussion and demonstrations of these two types of requests can be found on the [synchronous and asynchronous requests](synchronous_and_asynchronous_requests) page. Do not use synchronous requests outside Web Workers.

**Note:** Starting with Gecko 30.0 (Firefox 30.0 / Thunderbird 30.0 / SeaMonkey 2.27), synchronous requests on the main thread have been deprecated due to the negative effects to the user experience.

**Note:** The constructor function `XMLHttpRequest` isn't limited to only XML documents. It starts with **"XML"** because when it was created the main format that was originally used for Asynchronous Data Exchange were XML

Handling responses
------------------

There are several types of [response attributes](https://xhr.spec.whatwg.org/) defined by the living standard specification for the [`XMLHttpRequest()`](xmlhttprequest) constructor. These tell the client making the `XMLHttpRequest` important information about the status of the response. Some cases where dealing with non-text response types may involve some manipulation and analysis are outlined in the following sections.

### Analyzing and manipulating the responseXML property

If you use `XMLHttpRequest` to get the content of a remote XML document, the [`responseXML`](responsexml) property will be a DOM object containing a parsed XML document. This could prove difficult to manipulate and analyze. There are four primary ways of analyzing this XML document:

1.  Using [XPath](https://developer.mozilla.org/en-US/docs/Web/XPath) to address (or point to) parts of it.
2.  Manually [Parsing and serializing XML](https://developer.mozilla.org/en-US/docs/Web/Guide/Parsing_and_serializing_XML) to strings or objects.
3.  Using [`XMLSerializer`](../xmlserializer) to serialize **DOM trees to strings or to files**.
4.  [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) can be used if you always know the content of the XML document beforehand. You might want to remove line breaks, if you use `RegExp` to scan with regard to line breaks. However, this method is a "last resort" since if the XML code changes slightly, the method will likely fail.

**Note:** `XMLHttpRequest` can now interpret HTML for you using the [`responseXML`](responsexml) property. Read the article about [HTML in XMLHttpRequest](html_in_xmlhttprequest) to learn how to do this.

### Processing a responseText property containing an HTML document

If you use `XMLHttpRequest` to get the content of a remote HTML webpage, the [`responseText`](responsetext) property is a string containing the raw HTML. This could prove difficult to manipulate and analyze. There are three primary ways to analyze and parse this raw HTML string:

1.  Use the `XMLHttpRequest.responseXML` property as covered in the article [HTML in XMLHttpRequest](html_in_xmlhttprequest).
2.  Inject the content into the body of a [document fragment](../documentfragment) via `fragment.body.innerHTML` and traverse the DOM of the fragment.
3.  [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp) can be used if you always know the content of the HTML `responseText` beforehand. You might want to remove line breaks, if you use RegExp to scan with regard to linebreaks. However, this method is a "last resort" since if the HTML code changes slightly, the method will likely fail.

Handling binary data
--------------------

Although [`XMLHttpRequest`](../xmlhttprequest) is most commonly used to send and receive textual data, it can be used to send and receive binary content. There are several well tested methods for coercing the response of an `XMLHttpRequest` into sending binary data. These involve utilizing the [`overrideMimeType()`](overridemimetype) method on the `XMLHttpRequest` object and is a workable solution.

    var oReq = new XMLHttpRequest();
    oReq.open("GET", url);
    // retrieve data unprocessed as a binary string
    oReq.overrideMimeType("text/plain; charset=x-user-defined");
    /* ... */

However, more modern techniques are available, since the [`responseType`](responsetype) attribute now supports a number of additional content types, which makes sending and receiving binary data much easier.

For example, consider this snippet, which uses the `responseType` of "`arraybuffer`" to fetch the remote content into a [`ArrayBuffer`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) object, which stores the raw binary data.

    var oReq = new XMLHttpRequest();

    oReq.onload = function(e) {
      var arraybuffer = oReq.response; // not responseText
      /* ... */
    }
    oReq.open("GET", url);
    oReq.responseType = "arraybuffer";
    oReq.send();

For more examples check out the [Sending and Receiving Binary Data](sending_and_receiving_binary_data) page

Monitoring progress
-------------------

`XMLHttpRequest` provides the ability to listen to various events that can occur while the request is being processed. This includes periodic progress notifications, error notifications, and so forth.

Support for DOM `progress` event monitoring of `XMLHttpRequest` transfers follows the [specification for progress events](https://xhr.spec.whatwg.org/#interface-progressevent): these events implement the [`ProgressEvent`](../progressevent) interface. The actual events you can monitor to determine the state of an ongoing transfer are:

`progress`  
The amount of data that has been retrieved has changed.

`load`  
The transfer is complete; all data is now in the `response`

<!-- -->

    var oReq = new XMLHttpRequest();

    oReq.addEventListener("progress", updateProgress);
    oReq.addEventListener("load", transferComplete);
    oReq.addEventListener("error", transferFailed);
    oReq.addEventListener("abort", transferCanceled);

    oReq.open();

    // ...

    // progress on transfers from the server to the client (downloads)
    function updateProgress (oEvent) {
      if (oEvent.lengthComputable) {
        var percentComplete = oEvent.loaded / oEvent.total * 100;
        // ...
      } else {
        // Unable to compute progress information since the total size is unknown
      }
    }

    function transferComplete(evt) {
      console.log("The transfer is complete.");
    }

    function transferFailed(evt) {
      console.log("An error occurred while transferring the file.");
    }

    function transferCanceled(evt) {
      console.log("The transfer has been canceled by the user.");
    }

Lines 3-6 add event listeners for the various events that are sent while performing a data transfer using `XMLHttpRequest`.

**Note:** You need to add the event listeners before calling `open()` on the request. Otherwise the `progress` events will not fire.

The progress event handler, specified by the `updateProgress()` function in this example, receives the total number of bytes to transfer as well as the number of bytes transferred so far in the event's `total` and `loaded` fields. However, if the `lengthComputable` field is false, the total length is not known and will be zero.

Progress events exist for both download and upload transfers. The download events are fired on the `XMLHttpRequest` object itself, as shown in the above sample. The upload events are fired on the `XMLHttpRequest.upload` object, as shown below:

    var oReq = new XMLHttpRequest();

    oReq.upload.addEventListener("progress", updateProgress);
    oReq.upload.addEventListener("load", transferComplete);
    oReq.upload.addEventListener("error", transferFailed);
    oReq.upload.addEventListener("abort", transferCanceled);

    oReq.open();

**Note:** Progress events are not available for the `file:` protocol.

**Note:** Starting in Gecko 9.0, progress events can now be relied upon to come in for every chunk of data received, including the last chunk in cases in which the last packet is received and the connection closed before the progress event is fired. In this case, the progress event is automatically fired when the load event occurs for that packet. This lets you now reliably monitor progress by only watching the "progress" event.

**Note:** As of Gecko 12.0, if your progress event is called with a `responseType` of "moz-blob", the value of response is a [`Blob`](../blob) containing the data received so far.

One can also detect all three load-ending conditions (`abort`, `load`, or `error`) using the `loadend` event:

    req.addEventListener("loadend", loadEnd);

    function loadEnd(e) {
      console.log("The transfer finished (although we don't know if it succeeded or not).");
    }

Note there is no way to be certain, from the information received by the `loadend` event, as to which condition caused the operation to terminate; however, you can use this to handle tasks that need to be performed in all end-of-transfer scenarios.

Submitting forms and uploading files
------------------------------------

Instances of `XMLHttpRequest` can be used to submit forms in two ways:

-   using only AJAX
-   using the [`FormData`](../formdata) API

Using the `FormData` API is the simplest and fastest, but has the disadvantage that data collected can not be [stringified](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify).  
Using only AJAX is more complex, but typically more flexible and powerful.

### Using nothing but `XMLHttpRequest`

Submitting forms without the `FormData` API does not require other APIs for most use cases. The only case where you need an additional API is **if you want to upload one or more files**, where you use the [`FileReader`](../filereader) API.

#### A brief introduction to the submit methods

An html [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form) can be sent in four ways:

-   using the `POST` method and setting the `enctype` attribute to `application/x-www-form-urlencoded` (default);
-   using the `POST` method and setting the `enctype` attribute to `text/plain`;
-   using the `POST` method and setting the `enctype` attribute to `multipart/form-data`;
-   using the `GET` method (in this case the `enctype` attribute will be ignored).

Now, consider the submission of a form containing only two fields, named `foo` and `baz`. If you are using the `POST` method the server will receive a string similar to one of the following three examples, depending on the encoding type you are using:

-   Method: `POST`; Encoding type: `application/x-www-form-urlencoded` (default):

        Content-Type: application/x-www-form-urlencoded

        foo=bar&baz=The+first+line.%0D%0AThe+second+line.%0D%0A

-   Method: `POST`; Encoding type: `text/plain`:

        Content-Type: text/plain

        foo=bar
        baz=The first line.
        The second line.

-   Method: `POST`; Encoding type: `multipart/form-data`:

        Content-Type: multipart/form-data; boundary=---------------------------314911788813839

        -----------------------------314911788813839
        Content-Disposition: form-data; name="foo"

        bar
        -----------------------------314911788813839
        Content-Disposition: form-data; name="baz"

        The first line.
        The second line.

        -----------------------------314911788813839--

However, if you are using the `GET` method, a string like the following will be added to the URL:

    ?foo=bar&baz=The%20first%20line.%0AThe%20second%20line.

#### A little vanilla framework

All these effects are done automatically by the web browser whenever you submit a [`<form>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form). If you want to perform the same effects using JavaScript you have to instruct the interpreter about *everything*. Therefore, how to send forms in *pure* AJAX is too complex to be explained here in detail. For this reason, here we place **a complete (yet didactic) framework**, able to use all four ways to *submit*, and to **upload files**:

    <!doctype html>
    <html>
    <head>
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    <title>Sending forms with pure AJAX &ndash; MDN</title>
    <script type="text/javascript">

    "use strict";

    /*\
    |*|
    |*|  :: XMLHttpRequest.prototype.sendAsBinary() Polyfill ::
    |*|
    |*|  https://developer.mozilla.org/en-US/docs/DOM/XMLHttpRequest#sendAsBinary()
    \*/

    if (!XMLHttpRequest.prototype.sendAsBinary) {
      XMLHttpRequest.prototype.sendAsBinary = function(sData) {
        var nBytes = sData.length, ui8Data = new Uint8Array(nBytes);
        for (var nIdx = 0; nIdx < nBytes; nIdx++) {
          ui8Data[nIdx] = sData.charCodeAt(nIdx) & 0xff;
        }
        /* send as ArrayBufferView...: */
        this.send(ui8Data);
        /* ...or as ArrayBuffer (legacy)...: this.send(ui8Data.buffer); */
      };
    }

    /*\
    |*|
    |*|  :: AJAX Form Submit Framework ::
    |*|
    |*|  https://developer.mozilla.org/en-US/docs/DOM/XMLHttpRequest/Using_XMLHttpRequest
    |*|
    |*|  This framework is released under the GNU Public License, version 3 or later.
    |*|  https://www.gnu.org/licenses/gpl-3.0-standalone.html
    |*|
    |*|  Syntax:
    |*|
    |*|   AJAXSubmit(HTMLFormElement);
    \*/

    var AJAXSubmit = (function () {

      function ajaxSuccess () {
        /* console.log("AJAXSubmit - Success!"); */
        console.log(this.responseText);
        /* you can get the serialized data through the "submittedData" custom property: */
        /* console.log(JSON.stringify(this.submittedData)); */
      }

      function submitData (oData) {
        /* the AJAX request... */
        var oAjaxReq = new XMLHttpRequest();
        oAjaxReq.submittedData = oData;
        oAjaxReq.onload = ajaxSuccess;
        if (oData.technique === 0) {
          /* method is GET */
          oAjaxReq.open("get", oData.receiver.replace(/(?:\?.*)?$/,
              oData.segments.length > 0 ? "?" + oData.segments.join("&") : ""), true);
          oAjaxReq.send(null);
        } else {
          /* method is POST */
          oAjaxReq.open("post", oData.receiver, true);
          if (oData.technique === 3) {
            /* enctype is multipart/form-data */
            var sBoundary = "---------------------------" + Date.now().toString(16);
            oAjaxReq.setRequestHeader("Content-Type", "multipart\/form-data; boundary=" + sBoundary);
            oAjaxReq.sendAsBinary("--" + sBoundary + "\r\n" +
                oData.segments.join("--" + sBoundary + "\r\n") + "--" + sBoundary + "--\r\n");
          } else {
            /* enctype is application/x-www-form-urlencoded or text/plain */
            oAjaxReq.setRequestHeader("Content-Type", oData.contentType);
            oAjaxReq.send(oData.segments.join(oData.technique === 2 ? "\r\n" : "&"));
          }
        }
      }

      function processStatus (oData) {
        if (oData.status > 0) { return; }
        /* the form is now totally serialized! do something before sending it to the server... */
        /* doSomething(oData); */
        /* console.log("AJAXSubmit - The form is now serialized. Submitting..."); */
        submitData (oData);
      }

      function pushSegment (oFREvt) {
        this.owner.segments[this.segmentIdx] += oFREvt.target.result + "\r\n";
        this.owner.status--;
        processStatus(this.owner);
      }

      function plainEscape (sText) {
        /* How should I treat a text/plain form encoding?
           What characters are not allowed? this is what I suppose...: */
        /* "4\3\7 - Einstein said E=mc2" ----> "4\\3\\7\ -\ Einstein\ said\ E\=mc2" */
        return sText.replace(/[\s\=\\]/g, "\\$&");
      }

      function SubmitRequest (oTarget) {
        var nFile, sFieldType, oField, oSegmReq, oFile, bIsPost = oTarget.method.toLowerCase() === "post";
        /* console.log("AJAXSubmit - Serializing form..."); */
        this.contentType = bIsPost && oTarget.enctype ? oTarget.enctype : "application\/x-www-form-urlencoded";
        this.technique = bIsPost ?
            this.contentType === "multipart\/form-data" ? 3 : this.contentType === "text\/plain" ? 2 : 1 : 0;
        this.receiver = oTarget.action;
        this.status = 0;
        this.segments = [];
        var fFilter = this.technique === 2 ? plainEscape : escape;
        for (var nItem = 0; nItem < oTarget.elements.length; nItem++) {
          oField = oTarget.elements[nItem];
          if (!oField.hasAttribute("name")) { continue; }
          sFieldType = oField.nodeName.toUpperCase() === "INPUT" ? oField.getAttribute("type").toUpperCase() : "TEXT";
          if (sFieldType === "FILE" && oField.files.length > 0) {
            if (this.technique === 3) {
              /* enctype is multipart/form-data */
              for (nFile = 0; nFile < oField.files.length; nFile++) {
                oFile = oField.files[nFile];
                oSegmReq = new FileReader();
                /* (custom properties:) */
                oSegmReq.segmentIdx = this.segments.length;
                oSegmReq.owner = this;
                /* (end of custom properties) */
                oSegmReq.onload = pushSegment;
                this.segments.push("Content-Disposition: form-data; name=\"" +
                    oField.name + "\"; filename=\"" + oFile.name +
                    "\"\r\nContent-Type: " + oFile.type + "\r\n\r\n");
                this.status++;
                oSegmReq.readAsBinaryString(oFile);
              }
            } else {
              /* enctype is application/x-www-form-urlencoded or text/plain or
                 method is GET: files will not be sent! */
              for (nFile = 0; nFile < oField.files.length;
                  this.segments.push(fFilter(oField.name) + "=" + fFilter(oField.files[nFile++].name)));
            }
          } else if ((sFieldType !== "RADIO" && sFieldType !== "CHECKBOX") || oField.checked) {
            /* NOTE: this will submit _all_ submit buttons. Detecting the correct one is non-trivial. */
            /* field type is not FILE or is FILE but is empty */
            this.segments.push(
              this.technique === 3 ? /* enctype is multipart/form-data */
                "Content-Disposition: form-data; name=\"" + oField.name + "\"\r\n\r\n" + oField.value + "\r\n"
              : /* enctype is application/x-www-form-urlencoded or text/plain or method is GET */
                fFilter(oField.name) + "=" + fFilter(oField.value)
            );
          }
        }
        processStatus(this);
      }

      return function (oFormElement) {
        if (!oFormElement.action) { return; }
        new SubmitRequest(oFormElement);
      };

    })();

    </script>
    </head>
    <body>

    <h1>Sending forms with pure AJAX</h1>

    <h2>Using the GET method</h2>

    <form action="register.php" method="get" onsubmit="AJAXSubmit(this); return false;">
      <fieldset>
        <legend>Registration example</legend>
        <p>
          First name: <input type="text" name="firstname" /><br />
          Last name: <input type="text" name="lastname" />
        </p>
        <p>
          <input type="submit" value="Submit" />
        </p>
      </fieldset>
    </form>

    <h2>Using the POST method</h2>
    <h3>Enctype: application/x-www-form-urlencoded (default)</h3>

    <form action="register.php" method="post" onsubmit="AJAXSubmit(this); return false;">
      <fieldset>
        <legend>Registration example</legend>
        <p>
          First name: <input type="text" name="firstname" /><br />
          Last name: <input type="text" name="lastname" />
        </p>
        <p>
          <input type="submit" value="Submit" />
        </p>
      </fieldset>
    </form>

    <h3>Enctype: text/plain</h3>

    <form action="register.php" method="post" enctype="text/plain"
        onsubmit="AJAXSubmit(this); return false;">
      <fieldset>
        <legend>Registration example</legend>
        <p>
          Your name: <input type="text" name="user" />
        </p>
        <p>
          Your message:<br />
          <textarea name="message" cols="40" rows="8"></textarea>
        </p>
        <p>
          <input type="submit" value="Submit" />
        </p>
      </fieldset>
    </form>

    <h3>Enctype: multipart/form-data</h3>

    <form action="register.php" method="post" enctype="multipart/form-data"
        onsubmit="AJAXSubmit(this); return false;">
      <fieldset>
        <legend>Upload example</legend>
        <p>
          First name: <input type="text" name="firstname" /><br />
          Last name: <input type="text" name="lastname" /><br />
          Sex:
          <input id="sex_male" type="radio" name="sex" value="male" />
          <label for="sex_male">Male</label>
          <input id="sex_female" type="radio" name="sex" value="female" />
          <label for="sex_female">Female</label><br />
          Password: <input type="password" name="secret" /><br />
          What do you prefer:
          <select name="image_type">
            <option>Books</option>
            <option>Cinema</option>
            <option>TV</option>
          </select>
        </p>
        <p>
          Post your photos:
          <input type="file" multiple name="photos[]">
        </p>
        <p>
          <input id="vehicle_bike" type="checkbox" name="vehicle[]" value="Bike" />
          <label for="vehicle_bike">I have a bike</label><br />
          <input id="vehicle_car" type="checkbox" name="vehicle[]" value="Car" />
          <label for="vehicle_car">I have a car</label>
        </p>
        <p>
          Describe yourself:<br />
          <textarea name="description" cols="50" rows="8"></textarea>
        </p>
        <p>
          <input type="submit" value="Submit" />
        </p>
      </fieldset>
    </form>

    </body>
    </html>

To test this, create a page named **register.php** (which is the `action` attribute of these sample forms), and put the following *minimalistic* content:

    <?php
    /* register.php */

    header("Content-type: text/plain");

    /*
    NOTE: You should never use `print_r()` in production scripts, or
    otherwise output client-submitted data without sanitizing it first.
    Failing to sanitize can lead to cross-site scripting vulnerabilities.
    */

    echo ":: data received via GET ::\n\n";
    print_r($_GET);

    echo "\n\n:: Data received via POST ::\n\n";
    print_r($_POST);

    echo "\n\n:: Data received as \"raw\" (text/plain encoding) ::\n\n";
    if (isset($HTTP_RAW_POST_DATA)) { echo $HTTP_RAW_POST_DATA; }

    echo "\n\n:: Files received ::\n\n";
    print_r($_FILES);

The syntax to activate this script is:

    AJAXSubmit(myForm);

**Note:** This framework uses the [`FileReader`](../filereader) API to transmit file uploads. This is a recent API and is not implemented in IE9 or below. For this reason, the AJAX-only upload is considered **an experimental technique**. If you do not need to upload binary files, this framework works fine in most browsers.

**Note:** The best way to send binary content is via [`ArrayBuffers`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/ArrayBuffer) or [`Blobs`](../blob) in conjuncton with the [`send()`](send) method and possibly the [`readAsArrayBuffer()`](../filereader/readasarraybuffer) method of the `FileReader` API. But, since the aim of this script is to work with a [stringifiable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) raw data, we used the <span class="page-not-created">`sendAsBinary()`</span> method in conjunction with the [`readAsBinaryString()`](../filereader/readasbinarystring) method of the `FileReader` API. As such, the above script makes sense only when you are dealing with small files. If you do not intend to upload binary content, consider instead using the `FormData` API.

**Note:** The non-standard `sendAsBinary` method is considered deprecated as of Gecko 31 (Firefox 31 / Thunderbird 31 / SeaMonkey 2.28) and will be removed soon. The standard `send(Blob data)` method can be used instead.

### Using FormData objects

The [`FormData`](../formdata) constructor lets you compile a set of key/value pairs to send using `XMLHttpRequest`. Its primary use is in sending form data, but can also be used independently from a form in order to transmit user keyed data. The transmitted data is in the same format the form's `submit()` method uses to send data, if the form's encoding type were set to "multipart/form-data". FormData objects can be utilized in a number of ways with an `XMLHttpRequest`. For examples, and explanations of how one can utilize FormData with XMLHttpRequests, see the [Using FormData Objects](../formdata/using_formdata_objects) page. For didactic purposes here is **a *translation* of [the previous example](#a_little_vanilla_framework) transformed to use the `FormData` API**. Note the brevity of the code:

    <!doctype html>
    <html>
    <head>
    <meta http-equiv="Content-Type" charset="UTF-8" />
    <title>Sending forms with FormData &ndash; MDN</title>
    <script>
    "use strict";

    function ajaxSuccess () {
      console.log(this.responseText);
    }

    function AJAXSubmit (oFormElement) {
      if (!oFormElement.action) { return; }
      var oReq = new XMLHttpRequest();
      oReq.onload = ajaxSuccess;
      if (oFormElement.method.toLowerCase() === "post") {
        oReq.open("post", oFormElement.action);
        oReq.send(new FormData(oFormElement));
      } else {
        var oField, sFieldType, nFile, sSearch = "";
        for (var nItem = 0; nItem < oFormElement.elements.length; nItem++) {
          oField = oFormElement.elements[nItem];
          if (!oField.hasAttribute("name")) { continue; }
          sFieldType = oField.nodeName.toUpperCase() === "INPUT" ?
              oField.getAttribute("type").toUpperCase() : "TEXT";
          if (sFieldType === "FILE") {
            for (nFile = 0; nFile < oField.files.length;
                sSearch += "&" + escape(oField.name) + "=" + escape(oField.files[nFile++].name));
          } else if ((sFieldType !== "RADIO" && sFieldType !== "CHECKBOX") || oField.checked) {
            sSearch += "&" + escape(oField.name) + "=" + escape(oField.value);
          }
        }
        oReq.open("get", oFormElement.action.replace(/(?:\?.*)?$/, sSearch.replace(/^&/, "?")), true);
        oReq.send(null);
      }
    }
    </script>
    </head>
    <body>

    <h1>Sending forms with FormData</h1>

    <h2>Using the GET method</h2>

    <form action="register.php" method="get" onsubmit="AJAXSubmit(this); return false;">
      <fieldset>
        <legend>Registration example</legend>
        <p>
          First name: <input type="text" name="firstname" /><br />
          Last name: <input type="text" name="lastname" />
        </p>
        <p>
          <input type="submit" value="Submit" />
        </p>
      </fieldset>
    </form>

    <h2>Using the POST method</h2>
    <h3>Enctype: application/x-www-form-urlencoded (default)</h3>

    <form action="register.php" method="post" onsubmit="AJAXSubmit(this); return false;">
      <fieldset>
        <legend>Registration example</legend>
        <p>
          First name: <input type="text" name="firstname" /><br />
          Last name: <input type="text" name="lastname" />
        </p>
        <p>
          <input type="submit" value="Submit" />
        </p>
      </fieldset>
    </form>

    <h3>Enctype: text/plain</h3>

    <p>The text/plain encoding is not supported by the FormData API.</p>

    <h3>Enctype: multipart/form-data</h3>

    <form action="register.php" method="post" enctype="multipart/form-data"
        onsubmit="AJAXSubmit(this); return false;">
      <fieldset>
        <legend>Upload example</legend>
        <p>
          First name: <input type="text" name="firstname" /><br />
          Last name: <input type="text" name="lastname" /><br />
          Sex:
          <input id="sex_male" type="radio" name="sex" value="male" />
          <label for="sex_male">Male</label>
          <input id="sex_female" type="radio" name="sex" value="female" />
          <label for="sex_female">Female</label><br />
          Password: <input type="password" name="secret" /><br />
          What do you prefer:
          <select name="image_type">
            <option>Books</option>
            <option>Cinema</option>
            <option>TV</option>
          </select>
        </p>
        <p>
          Post your photos:
          <input type="file" multiple name="photos[]">
        </p>
        <p>
          <input id="vehicle_bike" type="checkbox" name="vehicle[]" value="Bike" />
          <label for="vehicle_bike">I have a bike</label><br />
          <input id="vehicle_car" type="checkbox" name="vehicle[]" value="Car" />
          <label for="vehicle_car">I have a car</label>
        </p>
        <p>
          Describe yourself:<br />
          <textarea name="description" cols="50" rows="8"></textarea>
        </p>
        <p>
          <input type="submit" value="Submit" />
        </p>
      </fieldset>
    </form>
    </body>
    </html>

**Note:** As we said, **[`FormData`](../formdata) objects are not [stringifiable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON/stringify) objects**. If you want to stringify a submitted data, use [the previous *pure*-AJAX example](#a_little_vanilla_framework). Note also that, although in this example there are some `file` [`<input>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input) fields, **when you submit a form through the `FormData` API you do not need to use the [`FileReader`](../filereader) API also**: files are automatically loaded and uploaded.

Get last modified date
----------------------

    function getHeaderTime () {
      console.log(this.getResponseHeader("Last-Modified"));  /* A valid GMTString date or null */
    }

    var oReq = new XMLHttpRequest();
    oReq.open("HEAD" /* use HEAD if you only need the headers! */, "yourpage.html");
    oReq.onload = getHeaderTime;
    oReq.send();

### Do something when last modified date changes

Let's create two functions:

    function getHeaderTime () {
      var nLastVisit = parseFloat(window.localStorage.getItem('lm_' + this.filepath));
      var nLastModif = Date.parse(this.getResponseHeader("Last-Modified"));

      if (isNaN(nLastVisit) || nLastModif > nLastVisit) {
        window.localStorage.setItem('lm_' + this.filepath, Date.now());
        isFinite(nLastVisit) && this.callback(nLastModif, nLastVisit);
      }
    }

    function ifHasChanged(sURL, fCallback) {
      var oReq = new XMLHttpRequest();
      oReq.open("HEAD" /* use HEAD - we only need the headers! */, sURL);
      oReq.callback = fCallback;
      oReq.filepath = sURL;
      oReq.onload = getHeaderTime;
      oReq.send();
    }

And to test:

    /* Let's test the file "yourpage.html"... */

    ifHasChanged("yourpage.html", function (nModif, nVisit) {
      console.log("The page '" + this.filepath + "' has been changed on " + (new Date(nModif)).toLocaleString() + "!");
    });

If you want to know ***if* *the current page* has changed**, please read the article about [`document.lastModified`](../document/lastmodified).

Cross-site XMLHttpRequest
-------------------------

Modern browsers support cross-site requests by implementing the [Cross-Origin Resource Sharing](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS) (CORS) standard. As long as the server is configured to allow requests from your web application's origin, `XMLHttpRequest` will work. Otherwise, an `INVALID_ACCESS_ERR` exception is thrown.

Bypassing the cache
-------------------

A cross-browser compatible approach to bypassing the cache is appending a timestamp to the URL, being sure to include a "?" or "&" as appropriate. For example:

    http://foo.com/bar.html -> http://foo.com/bar.html?12345
    http://foo.com/bar.html?foobar=baz -> http://foo.com/bar.html?foobar=baz&12345

As the local cache is indexed by URL, this causes every request to be unique, thereby bypassing the cache.

You can automatically adjust URLs using the following code:

    var oReq = new XMLHttpRequest();

    oReq.open("GET", url + ((/\?/).test(url) ? "&" : "?") + (new Date()).getTime());
    oReq.send(null);

Security
--------

**[Firefox 3 note](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/3)**

Versions of Firefox prior to Firefox 3 allowed you to set the preference `capability.policy.<policyname>.XMLHttpRequest.open</policyname>` to `allAccess` to give specific sites cross-site access. This is no longer supported.

**[Firefox 5 note](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Releases/5)**

Versions of Firefox prior to Firefox 5 could use `netscape.security.PrivilegeManager.enablePrivilege("UniversalBrowserRead");` to request cross-site access. This is no longer supported, even though it produces no warning and permission dialog is still presented.

The recommended way to enable cross-site scripting is to use the `Access-Control-Allow-Origin` HTTP header in the response to the XMLHttpRequest.

### XMLHttpRequests being stopped

If you conclude with an XMLHttpRequest receiving `status=0` and `statusText=null`, this means the request was not allowed to be performed. It was `UNSENT`. A likely cause for this is when the [`XMLHttpRequest` origin](https://www.w3.org/TR/2010/CR-XMLHttpRequest-20100803/#xmlhttprequest-origin) (at the creation of the XMLHttpRequest) has changed when the XMLHttpRequest is subsequently `open()`. This case can happen, for example, when one has an XMLHttpRequest that gets fired on an onunload event for a window, the expected XMLHttpRequest is created when the window to be closed is still there, and finally sending the request (in other words, `open()`) when this window has lost its focus and another window gains focus. The most effective way to avoid this problem is to set a listener on the new window's `activate` event which is set once the terminated window has its `unload` event triggered.

Workers
-------

Setting `overrideMimeType` does not work from a [`Worker`](../worker). See [bug 678057](https://bugzilla.mozilla.org/show_bug.cgi?id=678057) for more details. Other browsers may handle this differently.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://xhr.spec.whatwg.org/">XMLHttpRequest</a></td><td><span class="spec-living">Living Standard</span></td><td>Live standard, latest version</td></tr></tbody></table>

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

`Using_XMLHttpRequest`

1

12

1

7

5

Implemented via `ActiveXObject('Microsoft.XMLHTTP')`

8

1.2

1

18

4

10.1

1

1.0

`XMLHttpRequest`

1

12

1

7

≤12.1

3

1

18

4

≤12.1

1

1.0

`abort`

18

12

Yes

5

Yes

1.2

≤37

Yes

Yes

Yes

Yes

Yes

`abort_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`error_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`getAllResponseHeaders`

1

12

4

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

5

Yes

1.2

1

Yes

4

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

Yes

Yes

Yes

`getResponseHeader`

1

12

1

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

5

8

1.2

1

18

4

Starting from Firefox 49, empty headers are returned as empty strings in case the preference `network.http.keep_empty_response_headers_as_empty_string` is set to `true`, defaulting to `false`. Before Firefox 49 empty headers had been ignored. Since Firefox 50 the preference defaults to `true`.

10.1

1

1.0

`load_event`

Yes

≤79

Yes

9

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`loadend_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`loadstart_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`onreadystatechange`

1

12

1

5

9

1.2

1

18

4

10.1

1

1.0

`open`

1

12

1

Starting in Firefox 30, synchronous requests on the main thread have been deprecated due to their negative impact on performance and the user experience. Therefore, the `async` parameter may not be `false` except in a `Worker`.

5

8

1.2

1

18

4

Starting in Firefox 30, synchronous requests on the main thread have been deprecated due to their negative impact on performance and the user experience. Therefore, the `async` parameter may not be `false` except in a `Worker`.

10.1

1

1.0

`overrideMimeType`

1

12

Yes

11

5

Implemented via `ActiveXObject`

Yes

1.2

1

18

Yes

Yes

Yes

1.0

`progress_event`

Yes

≤79

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

?

Yes

`readyState`

1

12

1

7

8

1.2

1

18

4

10.1

1

1.0

`response`

9

12

6

10

11.6

5.1

≤37

18

6

12

6

1.0

`responseText`

1

12

1

5

Before Internet Explorer 10, the value of `XMLHttpRequest.responseText` could be read only once the request was complete.

8

1.2

1

18

4

10.1

1

1.0

`responseType`

31

12

6

10

12-15

18

7

55

55

50

42

7

6.0

`responseURL`

37

14

32

No

24

8

37

37

32

24

Yes

3.0

`responseXML`

Yes

12

Yes

Prior to Firefox 51, an error parsing the received data added a `<parsererror>` node to the top of the `Document` and then returned the `Document` in whatever state it happens to be in. This was inconsistent with the specification. Starting with Firefox 51, this scenario now correctly returns `null` as per the spec.

Yes

Yes

Yes

Yes

Yes

Yes

Prior to Firefox 51, an error parsing the received data added a `<parsererror>` node to the top of the `Document` and then returned the `Document` in whatever state it happens to be in. This was inconsistent with the specification. Starting with Firefox 51, this scenario now correctly returns `null` as per the spec.

Yes

Yes

Yes

`send`

1

12

1

5

8

1.2

1

18

4

10.1

1

1.0

`setRequestHeader`

1

12

1

5

8

1.2

1

18

4

10.1

1

1.0

`status`

1

12

1

7

Internet Explorer version 5 and 6 supported ajax calls using `ActiveXObject()`

8

1.2

1

18

4

10.1

1

1.0

`statusText`

1

12

1

7

Internet Explorer version 5 and 6 supported ajax calls using `ActiveXObject()`

Yes

1.2

1

18

4

Yes

Yes

1.0

`timeout`

29

12

12

8

17

12-16

6.1

≤37

29

14

18

12-16

7

2.0

`timeout_event`

Yes

≤18

Yes

10

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`upload`

1

12

Yes

10

Yes

10

1

18

Yes

Yes

Yes

1.0

`withCredentials`

3

12

3.5

Starting with Firefox 11, it's no longer supported to use the `withCredentials` attribute when performing synchronous requests. Attempting to do so throws an `NS_ERROR_DOM_INVALID_ACCESS_ERR` exception.

10

Internet Explorer versions 8 and 9 supported cross-domain requests (CORS) using [`XDomainRequest`](https://developer.mozilla.org/docs/Web/API/XDomainRequest).

12

4

≤37

18

4

Starting with Firefox 11, it's no longer supported to use the `withCredentials` attribute when performing synchronous requests. Attempting to do so throws an `NS_ERROR_DOM_INVALID_ACCESS_ERR` exception.

12

3.2

1.0

`worker_support`

4

Not supported in service workers.

12

Not supported in service workers.

3.5

Not supported in service workers.

10

Not supported in service workers.

10.6

Not supported in service workers.

4

Not supported in service workers.

4

Not supported in service workers.

18

Not supported in service workers.

4

Not supported in service workers.

11

Not supported in service workers.

5.1

Not supported in service workers.

1.0

Not supported in service workers.

See also
--------

1.  [MDN AJAX introduction](https://developer.mozilla.org/en-US/docs/Web/Guide/AJAX/Getting_Started)
2.  [HTML in XMLHttpRequest](html_in_xmlhttprequest)
3.  [HTTP access control](https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS)
4.  [How to check the security state of an XMLHTTPRequest over SSL](how_to_check_the_secruity_state_of_an_xmlhttprequest_over_ssl)
5.  [XMLHttpRequest - REST and the Rich User Experience](https://www.peej.co.uk/articles/rich-user-experience.html)
6.  [Microsoft documentation](https://msdn.microsoft.com/library/ms535874)
7.  ["Using the XMLHttpRequest Object" (jibbering.com)](https://jibbering.com/2002/4/httprequest.html)
8.  [The `XMLHttpRequest` object: WHATWG specification](https://xhr.spec.whatwg.org/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest</a>
