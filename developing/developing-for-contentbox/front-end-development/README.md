# Front-End Development

In developing your user interface, the majority of your time will be spent creating content in the admin and modifying files from within your custom theme, located in the `[ContentBox Module Home]/themes` directory.

With state-of-the art development tools like [CommandBox](http://commandbox.ortusbooks.com/content/) to assist with scaffolding and dependency management and [Coldbox Elixr](https://coldbox-elixir.ortusbooks.com/), it's easy to build out your theme in a fraction of the time it might otherwise take.

## Theme Directory Conventions

A typical theme directory structure might be:

###  MyAwesomeTheme

#### -  includes

*  css
*  fonts
*  js

#### -  layouts

#### -  templates

#### -  views

#### -  widgets

For more information on the theme directory structure and configuration options see [ContentBox Theme Development](https://contentbox.ortusbooks.com/developing/developing-for-contentbox/front-end-development/theme-development).

## Modularity

In addition, many front-end focused modules and libraries are available on Forgebox and can be installed from the [CommandBox](http://commandbox.ortusbooks.com/content/) CLI and used immediately in your templates, widgets and views. For example, to install a Twitter feed widget for ContentBox, simply run `box install ID=cbwidget-tweetfeed directory=widgets` from your theme directory and it will automatically be available for use in the admin. You may browse the ever-growing list of Forgebox libraries and modules on [Forgebox](https://forgebox.io/) or run `forgebox help` from within CommandBox to begin exploring the available options.

