# Working with Boilerplates and Docblocks in MDLCode

In Moodle™, it's expected that every PHP, JavaScript, and Mustache file starts with a standard boilerplate and includes a comment block. Here's what's expected for each file type:

- For PHP files: `@package`, `@copyright`, and `@license` tags in the comment block.
- For JavaScript files: `@module`, `@copyright`, and `@license` tags.
- For Mustache files: Only a `@template` tag.

Moodle™'s codechecker tool checks that the boilerplate includes specific lines. However, you can modify the first line to include your plugin's name and add more lines at the bottom.

## Setting Default Copyright

When you create a new PHP or JavaScript file in your plugin, MDLCode will automatically add a docblock with the copyright information. It uses the current year and the name you've set in the extension setting `mdlcode.copyright`.

![Setting Copyright](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/boilerplate/setting_copyright.png)

## Modifying Boilerplate and Docblock (Premium)

MDLCode allows you to save the default boilerplate for each plugin. To do this, place your cursor anywhere in the boilerplate and click the yellow lightbulb that appears on the left. Then, select "Save as default boilerplate for plugin..."

![Save Boilerplate](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/boilerplate/save_bp.png)

Now, when you create a new file in that plugin, MDLCode will use the saved boilerplate.

A similar feature is available for the docblock. It saves lines starting with `@copyright`, `@author`, and `@license`. This can be handy when working on different plugins with different copyright information.

When creating a new plugin using the MDLCode wizard, you can specify the default boilerplate and docblock for the plugin right in the wizard.

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
