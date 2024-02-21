
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

Two C++ SDKs are available, producing generally compatible results but
with certain technical tradeoffs.

* [`vamp-plugin-sdk`](https://github.com/vamp-plugins/vamp-plugin-sdk)
  is the original C++ SDK for writing both plugins and hosts. It
  supports all Vamp features and is compatible with C++11 or newer
  standards.
  * Plugins built with this SDK can be used in all Vamp hosts,
    although some hosts can only handle limited subsets of feature
    types regardless of the SDK used.
  * Hosts built with this SDK can load all Vamp plugins.
  
* [`rt-vamp-plugin-sdk`](https://github.com/lukasberbuer/rt-vamp-plugin-sdk)
  is an alternative C++ SDK for use in real-time performance-critical
  applications, supporting a limited set of output feature structures
  and requiring C++20 or newer.
  * Plugins built with this SDK can be used in all Vamp hosts. They
    can only return a limited set of feature types, but if your plugin
    requires only those feature types and you are confident this won't
    change, there is no technical disadvantage to using this SDK.
  * Hosts built with this SDK can load all Vamp plugins that use the
    same limited set of feature types. Those built with the "original"
    SDK can be used but will not be real-time safe.

### Tools for Testing Plugins and Hosts

* [`vamp-plugin-tester`](https://github.com/vamp-plugins/vamp-plugin-tester)
  is a command-line testing host for Vamp plugins. It runs a considerable
  number of tests and reports any problems it finds. It should be used
  before making any public release of a plugin.
  
* [`vamp-test-plugin`](https://github.com/vamp-plugins/vamp-test-plugin)
  is a test plugin for use when writing Vamp hosts. Unlike the Plugin
  Tester, it can't run any tests itself but provides a variety of
  different output types which you can use to check the behaviour of
  your host.

### Documentation

* [Programmer's Guide](https://vamp-plugins.org/guide.pdf) — the
  original official guide, currently available only in PDF form.

### License

In general the SDK and accompanying tools are provided under
permissive BSD/MIT license terms, to be used and redistributed in
software of any type. Please check the individual repositories for
more details.
