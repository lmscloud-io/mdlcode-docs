# Working with strings in MDLCode

## Lookup strings

When you see an identifier highlighted in orange it means that MDLCode detected a Moodle
entity.

### Hover to see the string value

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/strings/strings2.png">

In some cases you will see more than one string value, for example, when it is a help element
or the string has conditional concatenation.

### Ctrl+Click to go to the string definition

You can also right click and select "Go to definition" from the context menu.

### Detect references to non-existing strings

If you made a mistake in the string identifier, MDLCode will detect it and report as a problem.

## Lookup string references (Premium)

### Right click and select "Find all references" or "Go to references"

In the language file (PLUGINDIR/lang/en/PLUGINNAME.php) you can right click on the string
identifier and find all references to it.

### Identify unused strings

In the language file the string identifier that are not used will be reported as problems.

Please note that there can be false positives. You can add [directives.md](directives) to
disable problem reporting or advise Mdlcode about existing references.

## Create new strings (Premium)

### Create missing strings

If you see a problem 'String does not exist', place the cursor on the string identifier.
The yellow lightbulb will appear on the left. Click on it and select "Create string".

### Convert text to language string

Select the text that you want to convert. In PHP and JS files it has to be inside quotes, in MUSTACHE
files it can be anything except for tags and placeholders.

The yellow lightbulb will appear on the left. Click on it and select "Replace with new string ...".

If a language string with exactly the same contents already exists, you will also see actions
"Replace with existing string ..."

## Sort strings alphabetically (Premium)

Right click anywhere in a language file and select "Sort strings alphabetically" from the context menu.

If there is a comment "// Deprecated ..." in the file, the string identifiers after this comment
will not be sorted.

## Renaming strings (Premium)

Right-click on a string identifier in the language file and select "Rename symbol".
This will rename the string and all references to it.

Sometimes not all references can be renamed automatically, for example, when the string identifier
in a reference was created dynamically, or when string reference comes from a (directive)[directives.md].
In this case a popup will appear notifying you that some references could not be changed.
changed automatically