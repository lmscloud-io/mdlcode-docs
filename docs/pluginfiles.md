# Working with plugins in MDLCode

Moodle core has over 40 plugin types, for example `mod`, `block`, `tool`, `auth`, `enrol`,
`theme`, `local`, etc.

Some of the plugins define subplugin types, for example, `assignsubmission`, `assignfeedback`,
`logstore`, `quiz`, `tiny`, `atto` etc.

Each plugin type has its own folder in the Moodle codebase and these folders can be located
on different levels of the folder hierarchy.

## Plugins view

MDLCode introduces a "Moodle plugins" view that allows you to browse all plugins
in your Moodle codebase and can display all plugin types on the same level.

"Plugins" view allows you to switch between different view types:
- Group plugins by type / Show flat plugins list
- Show all plugins / Show only add-ons

Inside each plugin you will see the same files and directories structure as in the Explorer.

You can access this view by clicking on the Moodle icon in the Side Bar.

### Switching between Explorer and Plugins view

When you are working with the files and folders in the Plugins view you may notice
that the context menu items are different from the ones in the Explorer.

You can switch between the Explorer and Plugins view by selecting "Reveal in Explorer View"
and "Reveal in Moodle Plugins View" in the files context menu.

### Creating new folders in the Plugins view

When you are in the Plugins view and right click on the plugin name you will see that
"New folder" in the context menu is a sub-menu. Here you will find the suggestions for the
typical folders that can be created in the plugin, for example `amd`, `classes`, `db`, `lang`,
`templates`, etc.

When you right click on the `classes` folder for example and open "New folder" sub-menu
you will find there typical subfolders of this folder, for example, `task`, `event`, `form`,
`privacy`, `external`, etc.

You can always select "Other..." and type any name of the folder.

### Creating new files in the Plugins view

Similarly to the "New folder" sub-menu, the "New file" sub-menu will suggest you to create
typical files in the plugin, for example, `version.php`, `settings.php`, `lib.php`, etc under
the plugin folder and `access.php`, `services.php`, `upgrade.php`, etc. under the `db` folder.

When you create a new PHP file inside a Moodle plugin, MDLCode will automatically add
(boilerplate and docblock)[boilerplate.md]. If the file is a 'magic' file where Moodle
expects some specific contents, MDLCode will pre-populate the file with the skeleton of
the required code.

If you create a new JavaScript file in the `amd/src` folder, MDLCode will also automatically add
boilerplate and docblock with the module name.

If you create a new *.mustache file in the `templates` folder, MDLCode will automatically add
comments and template name.

Initial contents will be added even if you create a new file in the Explorer view. However, if
you create a new file outside of VSCode (for example, using a command line or a file manager),
the file will remain empty.
