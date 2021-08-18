# InstallTrigger.getVersion()

Parts of this page show the use of the [XPInstall API](https://developer.mozilla.org/en-US/docs/XPInstall_API_Reference). The majority of this API is now deprecated and as of Gecko 1.9 no longer available. [Extension](https://developer.mozilla.org/en-US/docs/Extensions), [Theme](https://developer.mozilla.org/en-US/docs/Themes), and [plug-in](https://developer.mozilla.org/en-US/docs/Plugins) developers must switch away from `install.js` based packages to the new [packaging scheme](https://developer.mozilla.org/en-US/docs/Bundles) with an `install.rdf` manifest. In particular plugin developers should see [how to package a plugin as an extension](https://developer.mozilla.org/en-US/docs/Shipping_a_plugin_as_a_Toolkit_bundle).

### getVersion

Returns an object representing the version number from the Client Version Registry for the specified component. It is used in both trigger scripts and installation scripts.

#### Method of

[InstallTrigger](../installtrigger) object

#### Syntax

    InstallVersion getVersion ( String component );

#### Parameters

The `getVersion` method has one parameter:

`component`  
The name of a component in the Client Version Registry.

#### Returns

If Software Installation is disabled, this method returns `NULL`. Otherwise, it returns an [InstallVersion](https://developer.mozilla.org/en-US/docs/XPInstall_API_Reference/InstallVersion_Object) object representing the version of the component.

If the component has not been registered in the Client Version Registry or if the specified component was installed with a null version, this method returns null.

Installing a component with a `NULL` version indicates that the component should always be updated when the opportunity arises.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/InstallTrigger/getVersion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/InstallTrigger/getVersion</a>
