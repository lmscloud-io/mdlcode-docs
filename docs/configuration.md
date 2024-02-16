# Configuration for MDLCode

Apart from setting [Copyright](boilerplate.md) or changing [CLI settings](runcli.md), you can also configure
[colors](configuration.md#colors-for-highlighting-entities) for highlighting Moodle™ entities,
change CodeLenses actions and other [features](configuration.md#enabled-features),
or set [problems to ignore](configuration.md#ignore-problems) to suppress problems.

## Colors for highlighting entities

Colors can only be configured using the `settings.json` file. To open it, select "Preferences: Open Settings (JSON)"
from the Command Palette.

If you don't specify anything it is equivalent to the following:

```json
{
  "mdlcode.decorations": {
    "default": {
      "dark": {
        "color": "#de481c"
      },
      "light": {
        "color": "#de481c"
      }
    }
  }
}
```

which means that all entities will be highlighted with the dark orange color:

![Default color dark](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/configuration/defaultdark.png)

![Default color light](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/configuration/defaultlight.png)


Overwrite decorations style for `default` (any entity) or for a specific entity types (`string`, `dbTable`, `jsModule`,
`capability`,  `formElement`, `callback`, `webservice`, `behatStep`, `template`,
`behatParamSelector`):

```json
{
  "mdlcode.decorations": {
    "capability": {
      "dark": {
        "backgroundColor": "#444444"
      },
      "light": {
        "backgroundColor": "#dddddd",
      },
    },
    "dbTable": {
      "border": "2px dashed rgba(211, 220, 50, .6)",
      "color": "#00ffff",
    },
    "string": {
      "color": "orange"
    }
  }
}
```

![Custom dark](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/configuration/customdark.png)

![Custom light](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/configuration/customlight.png)

## Enabled features

You can enable/disable some features in MDLCode or override their properties by adding them to the `mdlcode.features` setting.

Default value:

```json
    "mdlcode.features": {
        "rununittest.codelens": {
            "label": "Run test",
            "script": "{{php}} admin/tool/phpunit/cli/util.php --run --filter=\"{{method}}\" {{path}}"
        },
        "rununittests.codelens": {
            "label": "Run all tests",
            "script": "{{php}} admin/tool/phpunit/cli/util.php --run {{path}}"
        },
        "executetask.codelens": {
            "label": "Execute task",
            "script": "{{cliprefix}} {{php}} admin/cli/scheduled_task.php --execute={{class}}"
        }
    }
```

Each feature can be overridden separately, for example:

Hide the "Run test" CodeLens for individual test methods:

```json
        "rununittest.codelens": false,
```

Change the script and label for "Run all tests" CodeLens:

```json
        "rununittests.codelens": {
            "label": "Run all tests in this file",
            "script": "vendor/bin/phpunit {{path}}",
        }
```

Available placeholders:

- `{{path}}` - relative path to the file from the Moodle root directory (directory separator is always `/`, even on Windows)
- `{{fspath}}` - full path to the file with OS-specific separator (e.g. `C:\moodle\lib\file.php` or `/home/user/moodle/lib/file.php`)
- `{{file}}` - name of the file without the path
- `{{method}}` - name of the class method (when applicable)
- `{{class}}` - full name of the class with namespace (when applicable)
- `{{php}}` - PHP Path (from MDLCode settings, or by default `php`)
- `{{dirroot}}` - Moodle root directory
- `{{cliprefix}}` - Prefix for CLI command when executed as www user (from MDLCode setting `mdlcode.cli.prefix`)

All placeholders are replaced with escaped values (i.e. backslashes and quotes are escaped).

If you would like more placeholders to be added or more commands to have overrides, please [create an issue](https://github.com/lmscloud-io/mdlcode-docs/issues).

## Ignore problems

You can add [directives](directives.md) to ignore a specific problem (or all problems) in a file. However, if you
want to ignore a problem in all files, you can do it through the MDLCode settings.

Each problem type in MDLCode has a code. You can find this code in the "Problems" view, it will be displayed dimmed
in the brackets after the error message:

![Problem codes](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/configuration/problems.png)

Add this code to the "mdlcode.ignoreProblems" setting in MDLCode to mute problem notifications throughout the project.

Example:

```json
{
  "mdlcode.ignoreProblems": [
    "missing-docblock",
    "missing-boilerplate"
  ]
}
```
