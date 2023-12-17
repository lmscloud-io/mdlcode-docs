# Recommendations for Setting up VSCode for Moodle™ Development
2023-10-10
> Tutorial for developers who switch from other IDEs to VSCode.

[![Setting up VSCode for Moodle development](https://img.youtube.com/vi/iokOiSVNZ0Y/0.jpg)](https://youtu.be/UCjrNxKuGAY)

## Extensions featured in the video

* PHP [DEVSENSE.phptools-vscode](https://marketplace.visualstudio.com/items?itemName=DEVSENSE.phptools-vscode), also mentioned alternative: PHP Intelephense [bmewburn.vscode-intelephense-client](https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client)
* MDLCode — Moodle™ Plugin Development [LMSCloud.mdlcode](https://marketplace.visualstudio.com/items?itemName=LMSCloud.mdlcode)
* ESLint [dbaeumer.vscode-eslint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
* Mustache [dawhite.mustache](https://marketplace.visualstudio.com/items?itemName=dawhite.mustache)
* Snippets and Syntax Highlight for Gherkin (Cucumber) [stevejpurves.cucumber](https://marketplace.visualstudio.com/items?itemName=stevejpurves.cucumber)
* PHP Debug [xdebug.php-debug](https://marketplace.visualstudio.com/items?itemName=xdebug.php-debug)
* GitLens — Git supercharged [eamodio.gitlens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
* phpsc [shevaua.phpcs](https://marketplace.visualstudio.com/items?itemName=shevaua.phpcs), needs additional setup, see [here](#phpcs-extension-setup)
* Trailing Spaces [shardulm94.trailing-spaces](https://marketplace.visualstudio.com/items?itemName=shardulm94.trailing-spaces)
* PHP DocBlocker [neilbrayfield.php-docblocker](https://marketplace.visualstudio.com/items?itemName=neilbrayfield.php-docblocker)
* Table Formatter [shuworks.vscode-table-formatter](https://marketplace.visualstudio.com/items?itemName=shuworks.vscode-table-formatter)
* Database Client [cweijan.vscode-database-client2](https://marketplace.visualstudio.com/items?itemName=cweijan.vscode-database-client2)

## Recommended settings

```jsonc
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

  // Trailing spaces extension:
  "trailing-spaces.trimOnSave": true,
  "trailing-spaces.deleteModifiedLinesOnly": true,

  // PHP DocBlocker extension:
  "php-docblocker.defaultType": "mixed",
  "php-docblocker.useShortNames": true,

  // Code formatting in PHP (Devsense) extension:
  "[php]": {
    "editor.defaultFormatter": "DEVSENSE.phptools-vscode"
  },
  "php.completion.namingConvention": "snake_case",
  "php.format.rules.addCommaAfterLastArrayElement": true,
  "php.format.rules.declKeepRightParenAndOpenBraceOnOneLine": true,
  "php.format.rules.spaceAroundConcatenation": true,
  "php.format.rules.spaceBeforeParenthesesInControlStatements": true,
}
```

Following setting must be configured for your own environment:

```jsonc
{
  // MDLCode extension:
  "mdlcode.copyright": "Your Name",
  "mdlcode.cli.phpPath": "php",
  "mdlcode.cli.prefix": "sudo -u www-data",

  // phpcs extension:
  "phpcs.executablePath": "/path/to/moodle-plugin-ci/vendor/bin/phpcs"
}
```

## phpcs extension setup

First, install [moodle-plugin-ci](https://github.com/moodlehq/moodle-plugin-ci) anywhere outside of Moodle directory:

```bash
php composer.phar create-project moodlehq/moodle-plugin-ci /path/to/moodle-plugin-ci
```

To test `phpcs` run from your Moodle directory:

```bash
/path/to/moodle-plugin-ci/vendor/bin/phpcs index.php
```

When you test it you can set this path to `phpcs` in the setting `"phpcs.executablePath"`.

---

To explore other MDLCode features, refer to the [main documentation page](../docs/README.md).
