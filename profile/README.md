
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

* [`vamp-plugin-sdk`](https://github.com/vamp-plugins/vamp-plugin-sdk)
  is the original C++ SDK for writing both plugins and hosts in C++
  or, at a pinch, C. It supports all Vamp features and is compatible
  with the C++11 standard onwards.
  
* [`rt-vamp-plugin-sdk`](https://github.com/lukasberbuer/rt-vamp-plugin-sdk)
  is an alternative C++ SDK for use in real-time performance-critical
  applications, supporting a limited set of output feature structures
  and requiring C++20 or newer.
  * Plugins using the RT SDK can be used in all Vamp hosts, but can
    only return a limited set of feature types. If your plugin fits
    these limitations, there is no disadvantage to using this SDK.
  * Hosts using the RT SDK can load all plugins that use the same
    limited set of feature types, regardless of which SDK the plugins
    were written against.

