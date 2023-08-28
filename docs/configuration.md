# Configuration for MDLCode

Apart from setting [Copyright](boilerplate.md) or changing [CLI settings](runcli.md), you can also configure
[colors](configuration.md#colors-for-highlighting-entities) for highlighting Moodle™ entities
or [problems to ignore](configuration.md#ignore-problems) to suppress problems.

## Colors for highlighting entities

Colors can only be configured using the `settings.json` file. To open it, select "Preferences: Open Settings (JSON)"
from the Command Palette.

If you don't specify anything it is equivalent to the following:

```
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
```

which means that all entities will be highlighted with the dark orange color:

![Default color dark](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/configuration/defaultdark.png)

![Default color light](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/configuration/defaultlight.png)


Overwrite decorations style for `default` (any entity) or for a specific entity types (`string`, `dbTable`, `jsModule`,
`capability`,  `formElement`, `callback`, `webservice`, `behatStep`, `template`):

```
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

## Ignore problems

You can add [directives](directives.md) to ignore a specific problem (or all problems) in a file. However, if you
want to ignore a problem in all files, you can do it through the MDLCode settings.

Each problem type in MDLCode has a code. You can find this code in the "Problems" view, it will be displayed dimmed
in the brackets after the error message:

![Problem codes](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/configuration/problems.png)

Add this code to the "mdlcode.ignoreProblems" setting in MDLCode to mute problem notifications throughout the project.

Example:

```
{
  "mdlcode.ignoreProblems": [
    "missing-docblock",
    "missing-boilerplate"
  ]
}
```
