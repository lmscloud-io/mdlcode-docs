# Managing JavaScript Modules with MDLCode

The Moodle™ codebase includes various types of JavaScript files:
- ES6 modules (using 'import' and 'export')
- AMD modules (using 'define()')
- YUI modules - a legacy framework still in use in several places
- Plain JavaScript files like `module.js` or `block.js`

Additionally, you can embed JavaScript code in Mustache templates using the `{{#js}}` directive.

VSCode facilitates navigation between ES6 modules and functions. MDLCode goes a step further, aiding navigation between AMD and YUI modules, and detecting links from `*.php` and `*.mustache` files.

## Creating jsconfig.json

For VSCode to recognize module locations, you must create a `jsconfig.json` file and place it in your Moodle's root folder. To achieve this, use the command **"MDLCode: Create/update jsconfig.json for JS module resolution"** from the command palette.

## Navigating Between JS Modules

Whenever an orange-highlighted module name appears (in **php**, **js**, or **mustache** files), Ctrl+Click on it to access the module definition.

![Navigate](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/jsmodules/gotodefinition.png)

### Detecting Non-Existing Module References

If you mistakenly name or reference a module when importing it or in php or mustache files, MDLCode identifies the error and reports it as a problem.

## Exploring References (Premium)

Above the `@module` directive in the docblock of a JS file, you'll spot Code Lenses labeled "X references." Click this link or right-click a module name, then choose "Find all references."

![References](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/jsmodules/refs.png)

### Identifying Unused Modules

If a module remains unused in the code, it's flagged as a problem. Remember, there may be false positives. Use [directives](directives.md) to adjust problem reporting or inform MDLCode about existing references.

## Renaming JS Modules (Premium)

Right-click a module name after the `@module` directive and choose "Rename symbol." This not only renames the module but also updates the file name and modifies all references.

The new name doesn't have to be in the same folder. For instance, renaming `tool_plugin/welcome` to `tool_plugin/local/hello` will prompt MDLCode to create a `amd/src/local` folder, adjust the filename, and relocate it.

## Additional Features

### Fixing Module Names

Moodle coding standards recommend a docblock with a `@module` tag for each JS module. MDLCode identifies the module name in the docblock and suggests corrections if it doesn't match the file name.

Problems are reported if the module name is missing, the docblock is absent, or the module name is incorrect. Place your cursor on the problem, and a yellow lightbulb appears. Click it and select the appropriate command to fix the problem.

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
