Using XMLHttpRequest in IE6
===========================

[XMLHttpRequest](../xmlhttprequest) was first introduced by Microsoft in Internet Explorer 5.0 as an ActiveX control. However, in IE7 and other browsers XMLHttpRequest is a native JavaScript object.

In all modern browsers, you can create a new XMLHttpRequest object using the following code:

    var request = new XMLHttpRequest()

However, if you need to also support Internet Explorer 6 and older, you need to extend your code like this:

    if (window.XMLHttpRequest) {
        //Firefox, Opera, IE7, and other browsers will use the native object
        var request = new XMLHttpRequest();
    } else {
        //IE 5 and 6 will use the ActiveX control
        var request = new ActiveXObject("Microsoft.XMLHTTP");
    }

### See also

-   [Using XMLHttpRequest](using_xmlhttprequest)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest_in_IE6" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest/Using_XMLHttpRequest_in_IE6</a>
