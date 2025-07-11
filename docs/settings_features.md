# MDLCode settings. Enabled features

You can enable/disable some features in MDLCode or override their properties by adding them to the `mdlcode.features` setting.

Default value:

```json
    "mdlcode.features": {
        "rununittest.codelens": {
            "label": "Run test",
            "script": "{{php}} {{public}}admin/tool/phpunit/cli/util.php --run --filter='/::{{method}}$/' {{path}}"
        },
        "rununittests.codelens": {
            "label": "Run all tests",
            "script": "{{php}} {{public}}admin/tool/phpunit/cli/util.php --run {{path}}"
        },
        "executetask.codelens": {
            "label": "Execute task",
            "script": "{{cliprefix}} {{php}} {{public}}admin/cli/scheduled_task.php --execute={{class}}"
        },
        "runbehatscenario.codelens": {
          "script": "{{public}}admin/tool/behat/cli/run.php --feature=\"{{fspath}}:{{line}}\"",
          "label": "Run scenario"
        },
        "runbehatfeature.codelens": {
          "script": "{{public}}admin/tool/behat/cli/run.php --feature=\"{{fspath}}\"",
          "label": "Run scenario"
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

Run behat tests in docker in several environments:

```json
        "runbehatscenario.codelens": {
            "label": "Run in docker (php8.1, pgsql, firefox)",
            "script": "MOODLE_DOCKER_WWWROOT=\"{{dirroot}}\" moodle-docker-run-tests 1 --feature=/var/www/html/{{path}}:{{line}}"
        },
        "runbehatscenario.codelens2": {
            "label": "Run in docker (php8.2, mariadb, chrome)",
            "script": "MOODLE_DOCKER_WWWROOT=\"{{dirroot}}\" moodle-docker-run-tests 2 --feature=/var/www/html/{{path}}:{{line}}"
        },
```

See also a [tutorial on how to run Moodle behat/phpunit tests in docker](../tutorials/docker.md).


Available placeholders:

- `{{path}}` - relative path to the file from the Moodle root directory (directory separator is always `/`, even on Windows)
- `{{fspath}}` - full path to the file with OS-specific separator (e.g. `C:\moodle\lib\file.php` or `/home/user/moodle/lib/file.php`)
- `{{file}}` - name of the file without the path
- `{{line}}` - line number in the file
- `{{method}}` - name of the class method (when applicable)
- `{{class}}` - full name of the class with namespace (when applicable)
- `{{php}}` - PHP Path (from MDLCode settings, or by default `php`)
- `{{dirroot}}` - Moodle root directory
- `{{cliprefix}}` - Prefix for CLI command when executed as www user (from MDLCode setting `mdlcode.cli.prefix`)
- `{{public}}` - For Moodle 5.1+ - the public directory prefix (e.g. `public/`), for older versions - empty string.

All placeholders are replaced with escaped values (i.e. backslashes and quotes are escaped).

If you would like more placeholders to be added or more commands to have overrides, please [create an issue](https://github.com/lmscloud-io/mdlcode-docs/issues).
