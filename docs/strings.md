# Managing Language Strings with MDLCode

## Looking Up Strings

When you spot an orange-highlighted identifier, MDLCode has identified a Moodle™ entity.

### Hover for String Value

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/strings/strings2.png" title="String hover">

Sometimes, you might encounter multiple string values, such as for help elements or strings with conditional concatenation.

### Jump to String Definition

You can Ctrl+Click or right-click and select "Go to definition" from the context menu.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/strings/string_definition.png">

### Detecting Non-Existing String References

MDLCode spots errors in string identifiers and flags them as problems.

## Exploring String References (Premium)

### Finding All References

In the language file (`PLUGINDIR/lang/en/PLUGINNAME.php`), right-click on a string identifier, then select "Find all references", "Go to references", or "Peek > Peek references".

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/strings/string_references.png">

### Identifying Unused Strings

Unused string identifiers in the language file are reported as problems.

If you find any false positive errors,
consider using [directives](directives.md) to fine-tune problem reporting or provide information to MDLCode about existing references.

### Renaming Strings

Right-click a string identifier in the language file and select "Rename symbol". This will update the string and all references to it. Occasionally, references might not auto-update, such as with dynamically generated identifiers or when references come from [directives](directives.md). In such cases, a notification popup will appear.

## Creating New Strings (Premium)

### Generating Missing Strings

Encountering a 'String does not exist' issue? Click on the "Quick fix" link in the
error popup and choose "Create string."

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/strings/createstring1.png">

### Converting Text to Language String

Highlight the text you want to convert. In PHP and JS files, it should be enclosed in quotes; in MUSTACHE files, it can be any content except tags and placeholders. Click the yellow lightbulb icon on the left and select "Replace with new string ..."

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/strings/createstring2.png">

If an identical language string already exists, you'll also see the option "Replace with existing string ..."

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/strings/createstring3.png">

## Sorting Strings Alphabetically (Premium)

Place a mouse cursor on top of any text in the language file, click on the yellow lightbulb on the left and choose "Sort strings alphabetically".

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/strings/sortstrings.png">

Strings after a "// Deprecated ..." comment won't be sorted.

---

For more MDLCode features, refer to the [main documentation](README.md).