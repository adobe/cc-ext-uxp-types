## cc-ext-uxp-types

Type Definitions for Adobe UXP (Unified Extensibility Platform).


**UXP (Unified Extensibility Platform)** is powered by a modern JavaScript engine, offers a curated selection of UI components and a more streamlined workflow for plugin developers to build plugins for the UXP-powered Host Applications(e.g Adobe Photoshop, Adobe InDesign and Adobe XD).
UXP provides a set of common JavaScript APIs that are available in these Host Applications and the types are available for these common set of UXP JavaScript APIs in this repo.These types have been auto generated using an internal script within UXP codebase.

**Note**: Type definitions for the Host Application provided JavaScript APIs are present in separate repo and will need to be installed separately.

### Installation

Instructions for how to download/install the UXP Type Definitions onto your machine.

Example:
```
npm install @adobe/cc-ext-uxp-types
```

### Config
For using the UXP Type Definitions within your code editor, you need to create a tsconfig.json in your typescript project and add reference to the type declaration in compilerOptions.</br>
To make sure that UXP types do not conflict with the available web standard DOM types, update the required lib options to exclude these standard types.(Refer: https://www.typescriptlang.org/tsconfig#lib)</br>
Note: Please use jsconfig.json for JavaScript projects</br>

ts/jsconfig.json:
```
{
  "compilerOptions": {
    ...,
    // typeRoots override defaults, so be sure to include the implicit @types as well
    "typeRoots": [
      "node_modules/@types",
      "node_modules/@adobe/cc-ext-uxp-types",
      // Note that "DOM" is not included in lib options to exclude web DOM types
      "lib": ["ES2015"] // required ES version 
    ]
  }
}
```
Once you have setup the configuration, you will be able to leverage the type definitions for type suggestions, API usage and information, auto imports etc


### Licensing

See [LICENSE](LICENSE) for more information.
