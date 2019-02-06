# Umbraco SuperValueConverters

[![NuGet release](https://img.shields.io/nuget/v/Our.Umbraco.SuperValueConverters.svg)](https://www.nuget.org/packages/Our.Umbraco.SuperValueConverters/)
[![Our Umbraco project page](https://img.shields.io/badge/our-umbraco-orange.svg)](https://our.umbraco.com/projects/developer-tools/supervalueconverters/)

SuperValueConverters is a collection of powerful property value converters for Umbraco 7, eliminating the need for casting and null checks on Umbraco picker values in views or controllers and helping to keep code cleaner.

## Getting started

This package is supported on Umbraco 7.7+.

Once installed you don't need to do anything to activate SuperValueConverters.

### Installation

SuperValueConverters is available from Our Umbraco, NuGet, or as a manual download directly from GitHub.

#### Our Umbraco repository

You can find a downloadable package, along with a discussion forum for this package, on the [Our Umbraco](https://our.umbraco.com/projects/developer-tools/supervalueconverters/) site.

#### NuGet package repository

To [install from NuGet](https://www.nuget.org/packages/Our.Umbraco.SuperValueConverters/), run the following command in your instance of Visual Studio.

    PM> Install-Package Our.Umbraco.SuperValueConverters

## Usage

Where a picker that returns multiple items _(such as [MNTP](https://our.umbraco.com/documentation/Getting-Started/Backoffice/Property-Editors/Built-in-Property-Editors/Multinode-Treepicker2) or [Nested Content](https://our.umbraco.com/documentation/Getting-Started/Backoffice/Property-Editors/Built-in-Property-Editors/Nested-Content))_ has been configured to only allow a single item to be selected _(via it's "maxItems" setting)_, the returned value will now be a single `IPublishedContent` rather than `IEnumerable<IPublishedContent>`.

Even better - it works seamlessly with [Models Builder](https://our.umbraco.com/documentation/Reference/Templating/Modelsbuilder/) _(if you're using it)_ to return the correct model types from pickers rather than `IPublishedContent`. If a picker has been configured to only allow items of a specific doctype, the returned value's type will be already cast to the relevant model.

Supported value converters will no longer return `null` if no value has been picked - an empty collection will be returned instead, preventing the need for null checks.

Currently the following datatypes are supported:

* Media Picker
* Multi-Node Tree Picker
* Nested Content

### Contribution guidelines

To raise a new bug, create an issue on the GitHub repository. To fix a bug or add new features, fork the repository and send a pull request with your changes. Feel free to add ideas to the repository's issues list if you would to discuss anything related to the library.

### Who do I talk to?

This project is maintained by [Callum Whyte](https://callumwhyte.com/) and contributors. If you have any questions about the project please get in touch on [Twitter](https://twitter.com/callumbwhyte), or by raising an issue on GitHub.

## To do

* AppVeyor setup
* NuGet release

## License

Copyright &copy; 2019 [Callum Whyte](https://callumwhyte.com/), and other contributors

Licensed under the [MIT License](LICENSE.md).