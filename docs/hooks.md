# Working with Moodle™ Hooks in MDLCode

Hooks API is a new feature in Moodle 4.3 that allows plugins to customise core functionality
by implementing hook callbacks.
Hooks will eventually replace [callbacks](callbacks.md).

Unlike other entities in MDLCode, hooks are not highlighted in orange. Since they are
just class names, VSCode (with other PHP extensions) already allows to go to class
definition and/or find class references.

## Navigation between hooks definitions, emitters and callbacks

MDLCode adds Code Lenses to quickly navigate between hooks definitions, emitters and callbacks.

In the file db/hooks.php:

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/hooks/hooksphp.png">

In a class where hook callback is located:

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/hooks/hookcallback.png">

In a class where hook is defined:

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/hooks/hookdefinition.png">

Wherever a hook is emitted:

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/hooks/hookemitter.png">

(Hook callback lookup is a premium functionality.)

MDLCode also adds a Code Lens next to the legacy callbacks to indicate that they are already
converted to a hook callback.

## New Hook instance Wizard (Premium)

The Wizard allows to create a new hook instance in core or a plugin. It can also allow to
deprecate the existing callbacks and insert a hook emitter next to the get_plugins_with_function() call.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/hooks/newhook.png">

## New Hook callback Wizard (Premium)

The Wizard allows to create a new hook callback in core or a plugin. It can also allow to
migrate the existing legacy callback to a new hook callback.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/hooks/newhookcallback.png">

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
