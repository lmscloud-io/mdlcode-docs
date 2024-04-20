# Run Moodle behat/phpunit tests in docker
2024-04-20
> Configure MDLCode to run tests in docker with quick links above each test in the VSCode editor

## Setup

### 1. Install moodle-docker

Clone moodle-docker repository and check that you have docker installed (see [Prerequisites](https://github.com/moodlehq/moodle-docker?tab=readme-ov-file#prerequisites)).

```sh
git clone https://github.com/moodlehq/moodle-docker.git ~/moodle-docker
```

### 2. Configure Moodle instance

Copy `config.docker-template.php` to your Moodle instance directory:

```sh
cp ~/moodle-docker/config.docker-template.php /path/to/your/moodle
```

Add the following lines to the very end of your `config.php` (instead of including `lib/setup.php`):

```php
// Load moodle-docker config file if we are in moodle-docker environment
if (getenv('MOODLE_DOCKER_RUNNING')) {
    require_once(__DIR__ . '/config.docker-template.php');
}

require_once(__DIR__ . '/lib/setup.php');
```

**Important!** You need to do it for each Moodle instance where you want to run tests in docker.

### 3. Configure MDLCode

In VSCode open the Command Palette (Ctrl+Shift+P) and select `Preferences: Open User Settings (JSON)`, add the following code:

```json
    "mdlcode.features": {
        "runbehatscenario.codelens": {
            "label": "Run in docker (php8.1, pgsql, firefox)",
            "script": "MOODLE_DOCKER_WWWROOT=\"{{dirroot}}\" moodle-docker-run-tests 1 --feature=/var/www/html/{{path}}:{{line}}"
        },
        "runbehatscenario.codelens2": {
            "label": "Run in docker (php8.2, mariadb, chrome)",
            "script": "MOODLE_DOCKER_WWWROOT=\"{{dirroot}}\" moodle-docker-run-tests 2 --feature=/var/www/html/{{path}}:{{line}}"
        },
    }
```

You can modify this directive to change labels, add more environments, etc.

### 4. Create a script

Create an executable file `moodle-docker-run-tests` and place it in a PATH directory (e.g. `/usr/local/bin`). Use  [this template](https://gist.github.com/lmscloud-io/6935eb5b64993d6d6a5a89e5cb9aff5c) for this file. Modify it to specify the path to your docker, change the testing environments, etc.

### More...

<p>The full list of features you can change can be found in <a href="../docs/settings_features.md">MDLCode documentation</a>.</p>

For example, you can change the links on top of each behat file. Or you can run **phpunit** tests in the docker as well.