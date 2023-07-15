# Writing behat tests with MDLCode

## Step definition lookup

### Autocompletion

When you work on a scenario in a feature file, you can use autocomplete to insert a step.
To do it inside a scenario start typing "Given", "When", "Then" or "And", then type
space and any text, you will see a list of available steps that match the text you typed.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/behat/autocomplete.png">

### Ctrl+Click to go to the step definition

In feature files click anywhere in the step while holding the control key (or right click and
select "Go to definition").

In behat php files you will see that the first parameter for the "execute()" function is
highlighted with orange. Click on it while holding the control key (or right click and
select "Go to definition").

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/behat/gotodefinition.png">

### Right click and select "Find all references"

In the behat file (PLUGINDIR/tests/behat/behat_NAME.php) you can right click on the function
name and find all references to it - select
"Find all references", "Go to references" or "Peek > Peek references", whichever you prefer. This will search for references
in other behat files and in feature files.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/behat/references.png">

### Detect references to non-existing steps

If you made a mistake in the step definition, MDLCode will detect it and report as a problem.

## Miscellaneous diagnostics

MDLCode will report various types of problem in the feature files:
- duplicate feature names
- duplicate scenario names
- duplicate tags on a feature or scenario
- missing tags corresponding to the plugin type and/or plugin name on the feature
- unexpected lines in feature files
