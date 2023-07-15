# Working with Moodle callbacks in MDLCode

There are many places in Moodle core where it calls functions that are defined in
plugins.

In some cases it is one-to-many type of callback, which means that multiple
plugins can implement it and all of these callbacks will be executed.

In some cases it is one-to-one type of callback, which means that core looks for
a specific function in a particular plugin and will call it if found. There are
many such callbacks in Activity modules plugins, for example.

Normally callbacks are implemented in the file `lib.php` of the plugins.

MDLCode is aware of **all callbacks** used in Moodle core in each supported Moodle version.

Please note that add-on plugins theoretically may also define callbacks and MDLCode may not be
able to detect some of them.

## Detecting callbacks implementations

In `lib.php` file of the plugin MDLCode will detect the functions that are implementing
callbacks and display a Code Lens "Callback invokation" above the function definition.

The actual presense of this Code Lens will inform you that this function is a callback
implementation and clicking on this link will take you to all places in core where this
callback may be called. From there you can figure out **which parameters are expected**.

Intellisense extensions such as "PHP" (Devsense) or "PHP Intelephense" may report these
functions as having "0 references" because they are not called directly from the code.

## Callback search (Premium)

When you navigate to the place where callback is called from you will see a Code Lens
"Callback implementations" above the function that is calling the callback.

Clicking on this link will take you to all places in the code where this callback is
implemented.

## Callback autocomplete (Premium)

In the `lib.php` file in your plugin start typing "function ..." and you will see
the autocomplete list of all callbacks that are available for this plugin.

## New callback wizard (Premium)

New callback wizard will help you to choose a callback from the list of all callbacks available for this plugin type, and copy implementation from
another plugin. MDLCode also provides default implementation for some callbacks.

To open wizard do one of the following:
- inside `lib.php` file place the mouse cursor on any text and click
  on the yellow lightbulb that appears on the left side of the editor;
  select "Add callback" from the menu.
- click on the "New..." button in the Wizard view in the Moodle plugins
  view container.
