# Working with Moodle™ Callbacks in MDLCode

Numerous instances within the Moodle core involve calling functions defined within plugins.

In some cases, a **one-to-many** callback occurs, enabling multiple plugins to implement it, resulting in the execution of all corresponding callbacks.

Conversely, a **one-to-one** callback arises when the core searches for a specific function within a designated plugin and invokes it upon discovery. They are especially common in Activity module plugins.

Typically, callbacks implementations are found within the plugin's `lib.php` file.

MDLCode is aware of **all callbacks** used in Moodle core across supported Moodle™ versions.

However, please note that add-on plugins might potentially define callbacks that MDLCode can not detect.

## Identifying Callback Implementations

Within the plugin's `lib.php` file, MDLCode identifies functions that execute callbacks, displaying a Code Lens "Callback Invocation" above their definitions.

The presence of this Code Lens signifies a callback's implementation. Clicking this link guides you to instances within the core where this callback might be invoked. Consequently, you can discover **the expected parameters** for these instances.

![Callback with Arrow](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/callbacks/callback_with_arrow.png)

However, it's important to note that Intellisense extensions like "PHP" (Devsense) or "PHP Intelephense" may indicate "0 references" for these functions since they aren't directly invoked within the code.

## Callback Search (Premium)

Upon navigating to a callback's calling point, you'll spot a Code Lens "Callback Implementations" above the calling function.

Clicking this link leads you to various code locations where this callback is implemented.

![Invocation with Arrow](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/callbacks/invokation_with_arrow.png)

## Callback Autocomplete (Premium)

While editing the `lib.php` file within your plugin, start typing "function ...". The autocomplete list will promptly display all available callbacks for that plugin.

![Autocomplete](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/callbacks/autocomplete.png)

## New Callback Wizard (Premium)

The New Callback Wizard assists you in selecting a callback from the plugin-specific list, facilitating implementation copying from another plugin. Additionally, MDLCode supplies default implementations for certain callbacks.

To access the wizard, perform either of the following:
- Inside the `lib.php` file, position the cursor on any text, and click the yellow lightbulb situated on the editor's left side. Select "Add Callback" from the menu.
- In the Moodle plugins view container, click on the "New..." button within the Wizard view.

![Add Callback](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/callbacks/add.png)

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
