URLSearchParams.set()
=====================

The `set()` method of the [`URLSearchParams`](../urlsearchparams) interface sets the value associated with a given search parameter to the given value. If there were several matching values, this method deletes the others. If the search parameter doesn't exist, this method creates it.

**Note:** This feature is available in [Web Workers](../web_workers_api).

Syntax
------

    URLSearchParams.set(name, value)

### Parameters

`name`  
The name of the parameter to set.

`value`  
The value of the parameter to set.

### Return value

Void.

Examples
--------

Let's start with a simple example:

    let url = new URL('https://example.com?foo=1&bar=2');
    let params = new URLSearchParams(url.search);

    //Add a third parameter.
    params.set('baz', 3);
    params.toString(); // "foo=1&bar=2&baz=3"

Below is a real-life example demonstrating how to create a [`URL`](../url) and set some search parameters.

You can copy and paste the example in a code environment like Codepen, JSFiddle, or the [multi-line JavaScript interpreter in Firefox](https://developer.mozilla.org/en-US/docs/Tools/Web_Console/The_command_line_interpreter).

-   line \#41: Comment out this line to stop dumping the search parameters to the console (`debug()`).
-   line \#43: Dumps the generated object and its string representation to the console (`info()`).
-   line \#44: Tries to automatically open a new window/tab with the generated URL (when uncommented).

<!-- -->

    'use strict'

    function genURL(rExp, aText, bDebug=false){
        let theURL

        theURL= new URL('https://regexr.com')
        theURL.searchParams.set( 'expression', rExp.toString() )
        theURL.searchParams.set( 'tool', 'replace' )
        theURL.searchParams.set( 'input', '\u2911\u20dc' )// ⤑⃜
        theURL.searchParams.set( 'text', aText.join('\n') )
        if( bDebug ){
            // Display the key/value pairs
            for(var pair of theURL.searchParams.entries()) {
                console.debug(pair[0] + ' = \'' + pair[1] + '\'');
            }
            console.debug(theURL)
        }
        return theURL
    }
    var url = genURL(
        /(^\s*\/\/|\s*[^:]\/\/).*\s*$|\s*\/\*(.|\n)+?\*\/\s*$/gm   // single/multi-line comments
        // /(^\s*\/\/.*|\s*[^:]\/\/.*)/g                                // single-line comments
        ,[
            "These should work:",
            "",
            "// eslint-disable-next-line no-unused-vars",
            "lockPref(   'keyword.URL',\t\t'https://duckduckgo.com/html/?q=!+'   )\t//      test",
            "/*",
            "    * bla bla    ",
            "*/",
            "",
            "/* bla bla */",
            "",
            "// bla bla ",
            "",
            "These shouldn\'t work:",
            "console.log(\"http://foo.co.uk/\")",
            "var url = \"http://regexr.com/foo.html?q=bar\"",
            "alert(\"https://mediatemple.net\")",
        ]
        , true
    )
    console.info( url, url.toString() )
    // window.open( url, 'regex_site' )

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://url.spec.whatwg.org/#dom-urlsearchparams-set">URL<br />
<span class="small">The definition of 'set()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`set`

49

17

29

No

36

Yes

49

49

29

36

Yes

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/set" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/set</a>
