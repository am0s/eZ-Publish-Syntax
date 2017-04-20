eZ Publish ST2/3 Package
=====

This package offers:

* Syntax highlighting for .tpl (eZ Publish Template Language) and .ini (eZ INI) files
* Snippets

Compatible with Sublime Text 2 & 3

# Installation

Now available via package control!

Standard install: clone the repo into your Sublime Text "Packages" folder.

# Overriding syntax for .tpl files

By default Sublime Text will prefer to use HTML for files with the `.tpl` suffix.
By using the `ApplySyntax` package it is possible to setup rules based on
file path to override the syntax.

There are two ways, either a global rule that gets applied to any project
or per project.

The global rule is added by adding the file `ApplySyntax.sublime-settings` to
`Packages/User` and adding the content:

    {
        "syntaxes": [
            {
                "syntax": "ezp/eztemplate",
                "rules": [
                    {"file_path": ".*[\\\\/]design[\\\\/](admin|base|plain|standard)[\\\\/].*\\.(tpl|html)$"},
                    {"file_path": ".*[\\\\/]extension[\\\\/][^\\\\/]+[\\\\/]design[\\\\/][^\\\\/]+[\\\\/].*\\.(tpl|html)$"}
                ]
            }
        ]
    }

To instead set it per project edit the project (`Project / Edit Project`) and add:

    "settings": {
        "project_syntaxes": [
            {
                "syntax": "ezp/eztemplate",
                "extensions": ["tpl"]
            }
        ]
    }
