# Working with mustache templates in MDLCode

MDLCode makes it easier for you to work with mustache templates.

## Lookup templates

When you see an identifier highlighted in orange it means that MDLCode detected a Moodle
entity.

### Ctrl+Click to go to the templates

Mustache templates can be referenced from php files, from javascript files and from
other mustache templates.

You can either Ctrl+Click on a templates name hightlighted in orange or
right click and select "Go to definition" from the context menu.

This will take you to the `templates/NAME.mustache` file in the respective plugin where the template
is defined.

### Detect references to non-existing templates

If you made a mistake in the template name, MDLCode will detect it and report as a problem.

## Lookup references (Premium)

In the template file above the `@template` directive in the comment block you will see Code Lenses
"X references". You can either click on theis link or right click on a template name and select
"Find all references".

### Identify unused templates

If a template is not used anywhere in the code it will be reported as a problem.

Please note that there can be false positives. You can add [directives](directives.md) to
disable problem reporting or advise Mdlcode about existing references.

## Renaming templates (Premium)

Right-click on a template name after the `@template` directive and select "Rename symbol".
This will rename the template, rename the file and change all references to it.

The new name that you specify does not have to be in on the same level. For example, you can rename
template `tool_plugin/welcome` into `tool_plugin/local/hello` and MDLCode will automatically
create a folder `templates/local` and move the template there.

## Other features

### Fix template name

Moodle coding standards recommend that each template file has a comment with a `@template` tag. MDLCode
will detect the template name there and will suggest to fix the it if it does not
match the file name.

If the template name is missing, or the comment is missing, or the template name is incorrect
it will be reported as a problem. Place a cursor on the problem and a yellow lightbulb will
appear. Click on it and select appropriate command to fix the problem.
