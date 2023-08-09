# Working with DB Tables with MDLCode

## Lookup Table Names

An orange-highlighted identifier indicates that MDLCode has identified a Moodle entity.

MDLCode recognizes table names within function parameters like `$DB->get_records()` and `$DB->insert()`, as well as within curly brackets in SQL queries.

### Hover for Table Description

Hovering over a table reference displays its name and description. The description is extracted from the table comment in the `db/install.xml` file.

![Table Description](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/dbtables/dbtables1.png)

### Go to DB Table Definition

Ctrl+Click on an orange-highlighted table name or right-click and select "Go to definition" from the context menu.

This action leads you to the `db/install.xml` file in the relevant plugin where the DB table is defined.

![Go to Definition](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/dbtables/gotodefinition.png)

### Detecting Non-Existing Table References

MDLCode identifies errors in DB table names and flags them as problems.

## Exploring References (Premium)

In the `db/install.xml` file, above the table name, you'll encounter Code Lenses for "X code references" and
"Y test references." Click these links or right-click on a table name, then select "Find all references."

![References](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/dbtables/references.png)

### Identifying Unused DB Tables

In the `db/install.xml` file, unused table names are reported as problems. Keep in mind that there may be false positives. You can use [directives](directives.md) to adjust problem reporting or inform MDLCode about existing references.

## Renaming DB Tables (Premium)

Right-click a table name in the `db/install.xml` file and choose "Rename symbol." This updates the database table name and modifies all references to it.

Note that this action doesn't create an upgrade script for the renaming process; you'll need to do that separately using the XMLDB editor.

## Additional Features

### Detecting Duplicate Table Names

MDLCode identifies duplicate table names in the `db/install.xml` files and highlights them as problems.

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
