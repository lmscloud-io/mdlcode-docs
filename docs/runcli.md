# Running Moodle CLI scripts in MDLCode

* Select "MDLCode: Run CLI script" command from the command palette, or
* Open MDLCode Wizard and click "Run CLI script"

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/runcli/runcli.png">

## Before you run your first script

Open MDLCode settings and fill the path to PHP and the command to run as www user.
For your convenience the link to the extension settings is added to this panel.

Most of Moodle CLI scripts should be executed as the same user as your web server user,
usually it is either `www-data` or `www`. If you are not sure what user is used by your web server,
check the owner of the files in the `moodledata` directory.

If you run CLI scripts as the current user, it may create moodledata files with the
wrong owner and the web server will not be able to access or overwrite them.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/runcli/settings.png">

## Running CLI scripts

MDLCode creates two terminal windows - `"Moodle CLI (www)"` and `"Moodle CLI (current user)"`.
The first one is used to run scripts as the web server user, the second one - as the current user.

When executing scripts as the web server user, you might need to enter the password for `sudo` command.
Consequtive commands to this terminal will not ask for the password again. Neither MDLCode nor
other VSCode extensions can read the contents of the terminals or the password you enter.
MDLCode is only able to send commands to the terminal.

## Running arbitrary scripts

You can also run any scripts through this wizard. For this do not enter anything in the "CLI script"
field, select "Custom..." parameters and enter the command you want to run in the "Custom parameters" field.
For example, you can run `grunt` this way.

## Saving favourite CLI scripts (Premium)

You can save frequently used scripts to the favourites list. Favourite commands appear in the menu on the
right and also you can pick them from the command palette by selecting **"MDLCode: Run CLI script"**.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/runcli/palette.png">

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/runcli/runcliquickpick.png">

Here are some examples of the scripts that developers often use:

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
