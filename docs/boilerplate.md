# Working with boilerplate and docblock in MDLCode

Moodle expects that each php, js and mustache file has a standard boilerplate on the top of the
file and a comment block. For php files it expects `@package`, `@copyright` and `@license` tags
in the comment block. For js files it expects `@module`, `@copyright` and `@license`,
for template files it is only `@template` tag.

Moodle codechecker tool will verify that the boilerplate contains specific lines but you
can modify the first line to include the name of your plugin, for example, and add more lines
in the bottom.

## Setting default copyright

When you create a new php or js file in the plugin, MDLCode will automatically add a docblock
with the copyright. It will use current year and the name that you set in the extension setting
`mdlcode.copyright`.

## Modifying boilerplate and docblock (Premium)

With MDLCode you can save the default boilerplate for each plugin. To do it, place a cursor anywhere
in the boilerlate and click on the yellow lightbulb that appears on the left.
Select "Save as default boilerplate for plugin ..."

Now, when you create a new file in this plugin, MDLCode will use the boilerplate you saved.

Similar functionality is available for the docblock, however it will only save the lines that start
with `@copyright`, `@author` and `@license`. This functionality can be useful if you may work
on different plugins and use either your own name or the company name as a main copyright
depending on the plugin.

If you create a new plugin using the MDLCode wizard,
you can specify the default boilerplate and docblock for the plugin in the wizard.