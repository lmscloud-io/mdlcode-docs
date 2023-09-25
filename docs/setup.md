# Recommendations for Setting up VSCode for Moodle™ Development

Watch a video on how to setup VSCode for Moodle development:

[![Setting up VSCode for Moodle development](https://img.youtube.com/vi/iokOiSVNZ0Y/0.jpg)](https://youtu.be/iokOiSVNZ0Y)

Extensions featured in the video:
* PHP [DEVSENSE.phptools-vscode](https://marketplace.visualstudio.com/items?itemName=DEVSENSE.phptools-vscode)
* MDLCode [LMSCloud.mdlcode](https://marketplace.visualstudio.com/items?itemName=LMSCloud.mdlcode)
* ESLint [dbaeumer.vscode-eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
* Mustache [dawhite.mustache](https://marketplace.visualstudio.com/items?itemName=dawhite.mustache)
* Snippets and Syntax Highlight for Gherkin (Cucumber) [stevejpurves.cucumber](https://marketplace.visualstudio.com/items?itemName=stevejpurves.cucumber)
* PHP Debug [felixfbecker.php-debug](https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-debug)
* GitLens — Git supercharged [eamodio.gitlens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
* phpsc [shevaua.phpcs](https://marketplace.visualstudio.com/items?itemName=shevaua.phpcs), also see [moodle-plugin-ci](https://github.com/moodlehq/moodle-plugin-ci)
* Trailing Spaces [shardulm94.trailing-spaces](https://marketplace.visualstudio.com/items?itemName=shardulm94.trailing-spaces)
* PHP DocBlocker [neilbrayfield.php-docblocker](https://marketplace.visualstudio.com/items?itemName=neilbrayfield.php-docblocker)
* Table Formatter [shuworks.vscode-table-formatter](https://marketplace.visualstudio.com/items?itemName=shuworks.vscode-table-formatter)
* Database Client [cweijan.vscode-database-client2](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-database-client2)

Recommended settings:

```json
{
  "files.autoSave": "onFocusChange",
  "editor.detectIndentation": false,
  "[feature]": {
    "editor.tabSize": 2
  },
  "search.exclude": {
    "**/amd/build/**": true,
    "**/yui/build/**": true,
    "theme/*/style/*.css": true
  },
  "editor.stickyScroll.enabled": true,
  "editor.rulers": [132],
  "trailing-spaces.trimOnSave": true,
  "trailing-spaces.deleteModifiedLinesOnly": true,
  "php-docblocker.defaultType": "mixed",
  "php-docblocker.useShortNames": true,

  // Following setting must be configured for your own environment:
  "mdlcode.copyright": "Your Name",
  "mdlcode.cli.phpPath": "php",
  "mdlcode.cli.prefix": "sudo -u www-data",
  "phpcs.executablePath": "/path/to/moodle-plugin-ci/vendor/bin/phpcs"
}
```

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
