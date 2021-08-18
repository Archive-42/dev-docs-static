msCapsLockWarningOff
====================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `msCapsLockWarningOff` read/write property turns automatic caps lock warning on or off for validated password input fields.

This proprietary property is specific to Internet Explorer and Microsoft Edge.

Starting with Internet Explorer 10, input type=password fields will automatically display a warning if the caps lock is on. This property enables this warning to be disabled.

Syntax
------

    document.msCapsLockWarningOff = true;

Value
-----

Type: **boolean**

*False*: Default. Automatic caps lock warning is turned on.

*True*: Automatic caps lock warning is turned off.

Example
-------

Fiddle: <https://jsfiddle.net/jonathansampson/mqcHA/1/>

Example 2
---------

    <html>
    <head>
        <title>msCapsLockWarningOff example</title>
        <script type="text/javascript">

            function capsOff() {
                      if (document.msCapsLockWarningOff == false) {
                    document.msCapsLockWarningOff = true;
                    document.getElementById("caps").innerHTML = "Warning off";
                } else {
                    document.msCapsLockWarningOff = false;
                    document.getElementById("caps").innerHTML = "Warning on";
                }
            }

        </script>
    </head>
    <body>
    <label>Type a password: <input type="password" /></label><br />
    <button id="caps" onclick="capsOff();">Warning off</button>
    </body>
    </html>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/msCapsLockWarningOff" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/msCapsLockWarningOff</a>
