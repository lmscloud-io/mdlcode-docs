# Working with capabilities in MDLCode

## Lookup capabilities

When you see an identifier highlighted in orange it means that MDLCode detected a Moodle
entity.

### Hover to see the capability description

If you hover a capability reference you can see the name and the description.

### Ctrl+Click to go to the capability definition

You can either Ctrl+Click on a capability name hightlighted in orange or
right click and select "Go to definition" from the context menu.

This will take you to the `db/access.php` file in the respective plugin where the capability
is defined.

### Detect references to non-existing capabilities

If you made a mistake in the capabilitiy identifier, MDLCode will detect it and report as a problem.

## Language strings

In the `db/access.php` above the capability name you will see a Code Lens "Language string (en)".
Follow it to go to the `lang/en/` file and the string for this capability.

### Detect missing strings

Capability name in the `db/access.php` file without a corresponding string will be reported as a problem.

### Create missing strings (Premium)

Click on a yellow lightbulb nex to the problem and select "Create string"

## Lookup references (Premium)

In the `db/access.php` above the capability name you will see Code Lenses "X code references" and
"Y test references". You can either click on these links or right click on a capability name
and select "Find all references".

### Identify unused capabilities

In the `db/access.php` file the capabilities that are not used will be reported as problems.

Please note that there can be false positives. You can add [directives](directives.md) to
disable problem reporting or advise Mdlcode about existing references.

## Renaming capabilities (Premium)

Right-click on a capability name in the `db/access.php` file and select "Rename symbol".
This will rename the capability and all references to it, it will also rename the
language string with the capability name.
