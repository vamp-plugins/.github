
Developer Resources for Vamp Plugins
====================================

[Vamp](https://vamp-plugins.org/) is an audio processing plugin system
for plugins that extract descriptive information from audio data —
typically referred to as _audio analysis plugins_ or _audio feature
extraction plugins_.

You will find developer resources and information about the plugin
format here. Please refer to the [website](https://vamp-plugins.org/)
for user documentation and details about available plugins and hosts.

![Block diagram of Vamp plugin. Audio tracks feeding into a plugin which emits multiple possible output types: points, values, and grids.](https://vamp-plugins.org/images/vamp-overview-webscale.png)

### SDKs for Plugin and Host Development

Two SDKs are available, producing generally compatible results but
with certain technical tradeoffs.

* [`vamp-plugin-sdk`](https://github.com/vamp-plugins/vamp-plugin-sdk)
  is the original C++ SDK for writing both plugins and hosts. It
  supports all Vamp features and is compatible with C++11 or newer
  standards.
  * Plugins built with this SDK can be used in all Vamp hosts,
    although some hosts only support limited subsets of feature types
    regardless of the SDK used.
  * Hosts built with this SDK can load all Vamp plugins.
  
* [`rt-vamp-plugin-sdk`](https://github.com/lukasberbuer/rt-vamp-plugin-sdk)
  is an alternative C++ SDK for use in real-time performance-critical
  applications, supporting a limited set of output feature structures
  and requiring C++20 or newer.
  * Plugins built with this SDK can be used in all Vamp hosts. They
    can only return a limited set of feature types, but if your plugin
    requires only those feature types, there is no technical
    disadvantage to using this SDK.
  * Hosts built with this SDK can load all Vamp plugins that use the
    same limited set of feature types, although only those plugins
    built with the same RT SDK will be real-time safe.

