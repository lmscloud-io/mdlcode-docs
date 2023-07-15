# MDLCode: Moodle Plugin Development

VSCode extension that helps you with developing of Moodle plugins.

- Conveinient plugins navigation;
- Lookup of language strings, DB tables, callbacks, templates, web services, JS modules and other Moodle elements from PHP, JS and Mustache files;
- Identify mistyped references to Moodle elements;
- One-click creation of common files (`classes/*`, `db/*`, `lib.php`, `version.php`, etc.);
- and many more features.

**This extension is still under development, all premium features are free until October 2023.**

[Full documentation](https://github.com/lmscloud-io/mdlcode-docs/blob/main/docs/README.md)

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/strings/strings2.png">

## Other recommended extensions

MDLCode extension can parse PHP and JS files but it does not provide features of a language server.

In order to work with Moodle code you also need to install a **PHP IntelliSense** extension for VSCode,
for example [PHP Devsense](https://marketplace.visualstudio.com/items?itemName=DEVSENSE.phptools-vscode)
or [PHP Intelephense](https://marketplace.visualstudio.com/items?itemName=bmewburn.vscode-intelephense-client).

VSCode aleady has built-in support for JavaScript IntelliSense, but you might also want to install [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint).

There are also quite a few extensions that can help you with syntax highlighting and code formatting in Mustache and Behat feature files, for example
[dawhite.mustache](https://marketplace.visualstudio.com/items?itemName=dawhite.mustache) and
[stevejpurves.cucumber](https://marketplace.visualstudio.com/items?itemName=stevejpurves.cucumber).
