# Working with JavaScript modules in MDLCode

Moodle code contains several types of JavaScript files:
- ES6 modules (use 'import' and 'export')
- AMD modules (use 'define()')
- YUI modules - legacy framework that is still used in several places
- Plain JavaScript files such as `module.js` or `block.js`

You can also embed JavaScript code in Mustache templates using `{{#js}}` directive.

VSCode will help you to navigate between ES6 modules and functions. MDLCode will additionally
help you to navigate between AMD and YUI modules as well as detect links
from `*.php` and `*.mustache` files.

## Create jsconfig.json

In order for VSCode to know about the locations of the modules you need to create a file `jsconfig.json`
and place it in the root folder of your Moodle.

To do it you can select command **"MDLCode: Create/update jsconfig.json for JS module resolution"**
from the command palette.

## Navigate between JS modules

Whenever you see a module name highlighted in orange (in **php**, **js** or **mustache** files) you can
Ctrl+Click on it to navigate to the module definition.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/jsmodules/gotodefinition.png">

As mentioned above, VSCode intellisense will also help you to navigate between ES6 functions.

### Detect references to non-existing modules

If you made a mistake in the module name when importing it or refering to it from php or mustache files,
MDLCode will detect it and report as a problem.

## Lookup references (Premium)

In the JS file above the `@module` directive in the docblock you will see Code Lenses "X references".
You can either click on theis link or right click on a module name and select "Find all references".

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/jsmodules/refs.png">

### Identify unused modules

If a module is not used anywhere in the code it will be reported as a problem.

Please note that there can be false positives. You can add [directives](directives.md) to
disable problem reporting or advise Mdlcode about existing references.

## Renaming JS modules (Premium)

Right-click on a module name after the `@module` directive and select "Rename symbol".
This will rename the module, rename the file and change all references to it.

The new name that you specify does not have to be in on the same level. For example, you can rename
module `tool_plugin/welcome` into `tool_plugin/local/hello` and MDLCode will automatically
create a folder `amd/src/local`, rename the file and move it there.

## Other features

### Fix module name

Moodle coding standards recommend that each JS module has a docblock with a `@module` tag. MDLCode
will detect the module name in the docblock and will suggest to fix the module name if it does not
match the file name.

If the module name is missing, or the docblock is missing, or the module name is incorrect
it will be reported as a problem. Place a cursor on the problem and a yellow lightbulb will
appear. Click on it and select appropriate command to fix the problem.

