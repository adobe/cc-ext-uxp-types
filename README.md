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
     ..., // your existing configuration 
    // typeRoots override defaults, so be sure to include the implicit @types as well
    "typeRoots": [
      "node_modules/@types",
      "node_modules/@adobe/cc-ext-uxp-types"
    ],
    // Note that "DOM" is not included in lib options to exclude web DOM types
    "lib": ["ES2015"] // required ES version
  }
}
```
Once you have setup the configuration, you will be able to leverage the type definitions for type suggestions, API usage and information, auto imports etc

### Known Issues
* UXP code is primarily written in JavaScript, and not all parameters in the type definitions are explicitly specified with the accurate types. Consequently, you may encounter "any" types for some parameters.
* Type definitions for some of the UXP supported globals such as "window", "navigator" are not currently available.  
Please refer to the [UXP documentation](https://developer.adobe.com/photoshop/uxp/2022/uxp-api/) for the available types.
* Inherited properties show the names of derived class and not base class (known issue on the internal library being used ) for eg
  
 ```
  const document = new Document();
  document.isConnected();
  ```
  Type information will show ```isConnected``` as a property of ```Document``` (inherited) and not of the base class which is ```Node``` here.
* Typedef API suggestions would not appear when the element is created with the document.createElement API for eg:
```
const img = document.createElement("img");
```
```img``` would not show expected type suggestions as per the current limitation.
However an element created through constructor as below would show the correct type as expected:
```
const imgElement = new HTMLImageElement();
```


Please note that we will be gradually improving the type definitions and adding accurate types for UXP APIs along with some of the issues mentioned above.
If you encounter any issues or have suggestions for improvements, please feel free to report them as a github issue here.

### Licensing

See [LICENSE](LICENSE) for more information.
