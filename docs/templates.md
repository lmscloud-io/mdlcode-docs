# Streamlining Mustache Templates with MDLCode

MDLCode makes it easier for you to work with mustache templates.

## Exploring Templates

An orange-highlighted identifier signifies MDLCode's recognition of a Moodle entity.

### Navigating to Templates

Mustache templates can be referenced from php files, javascript files, and other mustache templates.

You can Ctrl+Click on an orange-highlighted template name or right-click and select "Go to definition" from the context menu.

![Navigate](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/templates/gotodefinition.png)

This action directs you to the `templates/NAME.mustache` file within the respective plugin where the template is defined.

### Detecting Non-Existing Template References

If you make an error in the template name, MDLCode promptly identifies it and marks it as a problem.

## Exploring References (Premium)

Within the template file, right above the `@template` directive in the comment block, you'll notice Code Lenses labeled "X references." You can either click this link or right-click on a template name and choose "Find all references."

![References](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/templates/references.png)

### Identifying Unused Templates

Unused templates within the code are highlighted as problems. However, remember that there might be instances of false positives. To address this, you can include [directives](directives.md) to adjust problem reporting or inform MDLCode about existing references.

## Renaming Templates (Premium)

Right-click a template name after the `@template` directive and select "Rename symbol." This action not only modifies the template name but also adjusts the filename and effectively updates all references to it.

Furthermore, the new name doesn't necessarily need to reside at the same level. For instance, renaming `tool_plugin/welcome` to `tool_plugin/local/hello` will prompt MDLCode to generate a `templates/local` folder and move the template there.

## Additional Features

### Correcting Template Names

As per Moodle's coding standards, every template file should include a comment with a `@template` tag. MDLCode automatically identifies the template name within this comment. If it doesn't match the file name, MDLCode suggests a **quick fix**.

If the template name is missing, the comment is absent, or the template name is incorrect, a problem is highlighted. To address it, position your cursor on the issue. A yellow lightbulb will appear. Click on it and choose the appropriate command to fix the problem.

![Name Fix](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/templates/namefix.png)

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
