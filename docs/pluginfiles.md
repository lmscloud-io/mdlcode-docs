# Exploring Plugins with MDLCode

Within Moodle™'s core, there are more than 40 plugin types such as `mod`, `block`, `tool`, `auth`, `enrol`,
`theme`, and `local`.

Some of these plugins define subplugin types like `assignsubmission`, `assignfeedback`,
`logstore`, `quiz`, `tiny`, `atto`, and more.

Each plugin type has its designated folder within the Moodle codebase, and these folders are organized at various levels in the directory structure.

## The Plugins View

MDLCode introduces a "Moodle plugins" view that simplifies browsing through all the plugins
in your Moodle codebase. This view can display all plugin types at the same hierarchy level.

The "Plugins" view offers the flexibility to switch between different display options:
- Group plugins by type / Show a flat list of plugins
- Show all plugins / Show only add-ons

Inside each plugin, you'll find a file and directory structure identical to what's in the Explorer.

You can access this view by clicking on the Moodle icon in the Side Bar.

![Plugins View](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/views/plugins_view.png)

### Switching between Explorer and Plugins View

While working within the Plugins view, you'll notice that the context menu items differ from those in the Explorer.

You can easily toggle between the Explorer and Plugins view by choosing "Reveal in Explorer View"
and "Reveal in Moodle Plugins View" from the file's context menu.

### Creating New Folders in the Plugins View

Within the Plugins view, right-clicking on a plugin name reveals a "New Folder" sub-menu. This sub-menu provides suggestions for common folders typically found within a plugin, like `amd`, `classes`, `db`, `lang`,
`templates`, and more.

For instance, if you right-click on the `classes` folder and open the "New Folder" sub-menu,
you'll find suggested subfolders like `task`, `event`, `form`,
`privacy`, `external`, and more.

You can also select "Other..." to input a custom folder name.

![Creating New Folders](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/views/new_folder.png)

### Creating New Files in the Plugins View

Similar to the "New Folder" sub-menu, the "New File" sub-menu offers suggestions for creating
common files within a plugin, such as `version.php`, `settings.php`, `lib.php`, etc., within
the plugin folder, and `access.php`, `services.php`, `upgrade.php`, etc., within the `db` folder.

![Creating New Files](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/views/new_file.png)

When you create a new PHP file within a Moodle plugin, MDLCode will automatically include the necessary [boilerplate and docblock](boilerplate.md). For files considered 'magic' where Moodle™ expects specific content, MDLCode will pre-fill the file with the required code structure.

Creating a new JavaScript file in the `amd/src` folder will also result in MDLCode adding relevant boilerplate and docblock information.

When you create a new *.mustache file within the `templates` folder, MDLCode will insert comments and the template name.

This initial content insertion even applies when creating a new file using the Explorer view. However, if you generate a new file outside of VSCode (e.g., through a command line or file manager), the file will remain empty.

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
