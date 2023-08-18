# Troubleshooting MDLCode

Table of contents:
* [MDLCode does not activate](#mdlcode-does-not-activate)
* [Entities are not highlighted while I type the code](#entities-are-not-highlighted-while-i-type-the-code)

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

---

To explore all MDLCode features, refer to the [main documentation page](README.md).
