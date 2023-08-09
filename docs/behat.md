# Writing Behat Tests with MDLCode

## Finding Step Definitions

### Using Autocompletion

While working on a scenario in a feature file, you can use autocomplete to insert a step.
To do this, type "Given", "When", "Then", or "And", followed by a space and any text. You will then see a list of available steps that match the text you typed.

![Autocompletion](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/behat/autocomplete.png)

### Navigating to Step Definitions

In feature files, you can click anywhere within a step while holding the control key (or right-click and
select "Go to definition").

![Go to Definition (Feature)](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/behat/gotodefinition_feature.png)

For Behat PHP files, you'll notice that the first parameter for the "execute()" function is
highlighted in orange. Click on it while holding the control key (or right-click and
select "Go to definition").

![Go to Definition](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/behat/gotodefinition.png)

### Finding All References

In the Behat file (`PLUGINDIR/tests/behat/behat_NAME.php`), you can right-click on a function
name to find all references to it. You can choose to "Find all references," "Go to references," or "Peek > Peek references," based on your preference. This search will extend to other Behat files and feature files.

![Find All References](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/behat/references.png)

### Detecting Non-Existing Steps

If you've made a mistake in the step definition, MDLCode will identify it and report it as a problem.

## Miscellaneous Diagnostics

MDLCode will identify various types of problems in feature files:
- Duplicate feature names
- Duplicate scenario names
- Duplicate tags on a feature or scenario
- Missing tags corresponding to the plugin type and/or plugin name on the feature
- Unexpected lines in feature files

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
