# MDLCode settings. Ignore problems

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
