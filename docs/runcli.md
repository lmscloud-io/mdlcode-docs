# Running Moodle CLI Scripts in MDLCode

* To run a CLI script, choose the "MDLCode: Run CLI script" command from the command palette, or
* Open the MDLCode Wizard and click "Run CLI script"

![Run CLI Script](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/runcli/runcli.png)

## Before Running Your First Script

Before executing your first script, access MDLCode settings and provide the PHP path and the command prefix to run a script as the www user. A link to the extension settings is conveniently available on this panel.

For most Moodle CLI scripts, running them as the same user as your web server user is recommended. Typically, this user is either `www-data` or `www`. To identify the user used by your web server, check the owner of files in the `moodledata` directory.

If you choose to run CLI scripts as the current user, keep in mind that it might lead to moodledata files being generated with incorrect owner. Consequently, the web server might not be able to access or modify these files.

![Settings](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/runcli/settings.png)

## Running CLI Scripts

MDLCode sets up two terminal windows: `"Moodle CLI (www)"` and `"Moodle CLI (current user)"`. The former is used to execute scripts as the web server user, while the latter is for the current user.

While running scripts as the web server user, you might need to input the `sudo` command password. Subsequent commands in this terminal won't ask for the password again. Remember, neither MDLCode nor other VSCode extensions can access terminal contents or the entered password. MDLCode can only send commands to the terminal.

## Running Custom Scripts

Through this wizard, you can also run custom scripts. Leave the "CLI script" field empty, choose "Custom..." parameters, and enter the desired command in the "Custom parameters" field. This approach enables you to execute commands like `grunt`.

## Code Integration

Beside scheduled tasks definitions, you'll find an "Execute task" code action. This serves as a shortcut to running a CLI script using `php admin/cli/scheduled_task.php --execute=CLASSNAME`.

![Execute Task](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/runcli/executetask.png)

## Saving Favorite CLI Scripts (Premium)

Save frequently used scripts to your favorites list. These preferred commands will appear in the right-click menu and can also be accessed from the command palette using **"MDLCode: Run CLI script"**.

![Favorites in Right-Click Menu](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/runcli/palette.png)

![Quick Pick for Favorites](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/runcli/runcliquickpick.png)

Here are some examples of commonly used developer scripts:

<table>
<tr>
<th>Run cron</th>
<td><pre>admin/cli/cron.php</pre></td>
<td>www</td>
</tr>
<tr>
<th>Init phpunit</th>
<td><pre>admin/tool/phpunit/cli/init.php</pre></td>
<td>current user</td>
</tr>
<tr>
<th>Purge caches</th>
<td><pre>admin/cli/purge_caches.php</pre></td>
<td>www</td>
</tr>
<tr>
<th>Set developer debugging</th>
<td><pre>admin/cli/cfg.php --name=debug --set=32767</pre></td>
<td>www</td>
</tr>
<tr>
<th>Upgrade</th>
<td><pre>admin/cli/upgrade.php --non-interactive</pre></td>
<td>www</td>
</tr>
</table>

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
