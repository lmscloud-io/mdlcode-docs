# MDLCode settings. Colors for highlighting entities

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
