InstallTrigger
==============

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `InstallTrigger` interface is an interesting outlier in the Apps API; it's included in this API but are inherited from the old Mozilla XPInstall technology for installing add-ons. It is used for triggering the download and installation of an add-on (or anything packaged in an .`xpi` file) from a Web page, using JavaScript code to kick off the install process.

**Note:** This article needs to be updated somewhat.

Overview
--------

For very simple installations, the install methods on the `InstallTrigger` object may be all that's needed in the installation script.

For more complex installations, you may need to use the [Install](https://developer.mozilla.org/en-US/docs/XPInstall_API_Reference/Install_Object) and/or [File](https://developer.mozilla.org/en-US/docs/XPInstall_API_Reference/File_Object) installation objects. In either case, you must trigger the installation process by creating a web page script in which InstallTrigger methods download the specified XPI file and "trigger" the execution of the install.js script at the top level of that XPI.

The principal method on the InstallTrigger object is [install](installtrigger/install), which downloads and installs one or more software packages archived in the XPI file format. The following is a basic example of an install trigger on a web page:

    xpi={'XPInstall Dialog Display Name':'simple.xpi'};
    InstallTrigger.install(xpi);

You can also use the InstallTrigger object to install Netscape 6/Mozilla skins and language packs, and perform multiple-package installations with [install](installtrigger/install).

[InstallTrigger.compareVersion](installtrigger/compareversion)  
Compares the version of a file or package with the version of an existing file or package.

[InstallTrigger.enabled](installtrigger/enabled)  
Indicates whether or not Software Installation is enabled for this client machine.

[InstallTrigger.getVersion()](installtrigger/getversion)  
Parts of this page show the use of the [XPInstall API](https://developer.mozilla.org/en-US/docs/XPInstall_API_Reference). The majority of this API is now deprecated and as of Gecko 1.9 no longer available. [Extension](https://developer.mozilla.org/en-US/docs/Extensions), [Theme](https://developer.mozilla.org/en-US/docs/Themes), and [plug-in](https://developer.mozilla.org/en-US/docs/Plugins) developers must switch away from `install.js` based packages to the new [packaging scheme](https://developer.mozilla.org/en-US/docs/Bundles) with an `install.rdf` manifest. In particular plugin developers should see [how to package a plugin as an extension](https://developer.mozilla.org/en-US/docs/Shipping_a_plugin_as_a_Toolkit_bundle).

[InstallTrigger.install](installtrigger/install)  
Installs one or more XPI files on the local machine.

[InstallTrigger.installChrome](installtrigger/installchrome)  
Installs new skin or locale packages in Netscape 6 and Mozilla.

[InstallTrigger.startSoftwareUpdate](installtrigger/startsoftwareupdate)  
Triggers the downloading and installation of the software at the specified URL.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InstallTrigger" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InstallTrigger</a>
