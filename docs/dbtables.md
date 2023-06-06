# Working with DB tables in MDLCode

## Lookup tables

When you see an identifier highlighted in orange it means that MDLCode detected a Moodle
entity.

MDLCode will detect the table names in the parameters of the functions such as
`$DB->get_records()`, `$DB->insert()` and also in curly brackets in the SQL queries.

### Hover to see the table description

If you hover a table reference you can see the name and the description. Description
is taken from the table comment in the `db/install.xml` file.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/dbtables/dbtables1.png">

### Ctrl+Click to go to the db table definition

You can either Ctrl+Click on a table name hightlighted in orange or
right click and select "Go to definition" from the context menu.

This will take you to the `db/install.xml` file in the respective plugin where the db table
is defined.

### Detect references to non-existing tables

If you made a mistake in the DB table name, MDLCode will detect it and report as a problem.

## Lookup references (Premium)

In the `db/install.xml` above the table name you will see Code Lenses "X code references" and
"Y test references". You can either click on these links or right click on a table name
and select "Find all references".

### Identify unused DB tables

In the `db/install.xml` file the table names that are not used will be reported as problems.

Please note that there can be false positives. You can add [directives](directives.md) to
disable problem reporting or advise Mdlcode about existing references.

## Renaming DB tables (Premium)

Right-click on a table name in the `db/install.xml` file and select "Rename symbol".
This will rename the database table and change all references to it.

Note that this will not create an upgrade script for the rename, you have to do it separately
using XMLDB editor.

## Other features

### Detect duplicate table names

MDLCode will detect duplicate table names in the `db/install.xml` files and highlight them as problems.