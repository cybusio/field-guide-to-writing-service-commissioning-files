[![Powered by Cybus](https://img.shields.io/badge/powered%20by-Cybus-yellow.svg?colorB=fca51f)](https://cybus.io)

# IDE Setup for Visual Studio

Working on VSCode with Service Commissioning File can be simplified a bit 
by supporting the additional yaml custom tags the Cybus Connectware provides for files [as documented](https://docs.cybus.io/latest/user/services/structure/parameters.html#user-services-structure-parameters).

Doing so avoids error messages created by a Yaml syntax checker when 
using these tags, which is regular for service commissioning files.

This means also to commit a VSCode settings file into your source code
repository (actually an antipattern for IDE meta files, but a good practice
in this case):

The custom tags for yaml are defined this way:
```
{
  "yaml.customTags": [
      "!sub",
      "!ref",
      "!merge"
  ]
}
```

You should then add this to your .gitignore file in order to ensure
that nothing but this settings.json file is commited:

```
.vscode/*
!.vscode/settings.json
```