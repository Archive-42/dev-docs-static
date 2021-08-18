InstallTrigger.startSoftwareUpdate
==================================

Summary
-------

Triggers the downloading and installation of the software at the specified URL.

### Method of

[InstallTrigger](../installtrigger) object

Syntax
------

    Boolean startSoftwareUpdate ( String url);

### Parameters

The `startSoftwareUpdate` method has the following parameter:

`url`  
A uniform resource locator specifying the location of the XPI file containing the software.

### Returns

True.

Description
-----------

The `startSoftwareUpdate` method triggers a software download and install from the specified URL. This method has been largely superseded by newer [install](install) method, which is more flexible and allows you to install more than one XPI. Note also that XPIs installed with this method must have their own install.js files in which the full installation is defined.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InstallTrigger/startSoftwareUpdate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InstallTrigger/startSoftwareUpdate</a>
