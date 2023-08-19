# Troubleshooting MDLCode

Table of contents:
* [MDLCode does not activate](#mdlcode-does-not-activate)
* [Entities are not highlighted while I type the code](#entities-are-not-highlighted-while-i-type-the-code)
* [Index seems out of date](#index-seems-out-of-date)

## MDLCode does not activate

MDLCode will activate automatically if it detects a Moodle instance as a root of one of the VSCode Workspace folders.

MDLCode **will not activate** if Moodle is **not a root folder**, for example, if you open a parent folder
that contains both Moodle instance and moodledata folder. If this is something you would like to do,
consider creating a [Multi-root workspace](https://code.visualstudio.com/docs/editor/workspaces) where
Moodle instance and moodledata folder are separate roots.

If you have a multi-root workspace and you opened several Moodle instances, MDLCode will activate
**only for the first Moodle instance**.

Once MDLCode is activated, it will add a Moodle icon to the Side Bar. It will also start full index
of the Moodle instance. Initial reindex may take some time.

![Activation](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/troubleshooting/activation.png)

Until full index is completed some features may not be available. You can see the progress in the status bar.

When you open the same Moodle instance again, reindex will be much faster.

## Entities are not highlighted while I type the code

MDLCode can only detect entities in the PHP and JavaScript files that do not have syntax errors. While
you type the code, the file may not be syntactically correct (missing brackets, quotes, etc.) and
MDLCode will not be able to detect entities.

## Index seems out of date

MDLCode tries to automatically re-index files that are changed. If you notice that some entities are not
highlighted or references search does not work, or new entities do not appear in the lists,
you can do the following:

- If the problem is in MDLCode Wizard, try closing it and opening again;
- If the plugins or files list in the "Plugins" view is out of date, try clicking the "Refresh" button;
- If the problem is in the code editor, try making any change to the file, switching to another tab and back;
- Finally you can force full reindex by selecting "MDLCode: Re-index all files in this Moodle instance"
  from the Command Palette. This will perform "slow" re-index that does not use any caches.

![Re-index](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/troubleshooting/reindex.png)

If you can reproduce the scenario when MDLCode does not re-index something automatically, please
[create an issue](https://github.com/lmscloud-io/mdlcode-docs/issues) and describe how to reproduce it.

---

To explore all MDLCode features, refer to the [main documentation page](README.md).
