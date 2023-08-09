# Navigating Capabilities with MDLCode

## Lookup Capability Names

An orange-highlighted identifier signifies MDLCode's recognition of a Moodle entity.

### Hover for Capability Description

Hovering over a capability reference reveals its name and description.

### Jump to Capability Definition

Ctrl+Click on an orange-highlighted capability name or right-click and select "Go to definition" from the context menu.

![Go to Definition](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/capabilities/gotodefinition.png)

This action directs you to the `db/access.php` file within the relevant plugin, where the capability is defined.

### Detecting Non-Existing Capability References

MDLCode identifies errors in capability identifiers and highlights them as problems.

## Language Strings

Above the capability name in the `db/access.php` file, you'll find a Code Lens "Language string (en)." Clicking it takes you to the corresponding string in the `lang/en/` file.

![Language String](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/capabilities/langstring.png)

### Detecting Missing Strings

Capability names without corresponding strings in the `db/access.php` file are flagged as problems.

### Generating Missing Strings (Premium)

Click on a yellow lightbulb next to the problem and select "Create string."

## Exploring References (Premium)

Above the capability name in the `db/access.php` file, you'll encounter Code Lenses for "X code references" and
"Y test references." Click these links or right-click on a capability name, then choose "Find all references."

### Identifying Unused Capabilities

Unused capabilities within the `db/access.php` file are reported as problems. Keep in mind that there might be false positives. You can use [directives](directives.md) to modify problem reporting or inform MDLCode about existing references.

## Renaming Capabilities (Premium)

Right-click a capability name in the `db/access.php` file and select "Rename symbol." This action not only renames the capability itself but also updates all references to it, including the associated language string.

## New Capability Wizard (Premium)

Place your cursor on any text within the `db/access.php` file and click the yellow lightbulb. Select "Add capability."

You can also access this feature from the "Wizard" view by clicking the "New..." button.

![New Capability Wizard](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/capabilities/wizard.png)

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
