# Executing Web Services in MDLCode

* Open MDLCode Wizard and click "Execute WebService", or
* Click on "Execute WS" next to the service definition or implementation

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/executews/launch.png">

## Setting up WebServices

Before you can execute a WebService, you need to set up the environment. You need to enable
WebServices in your Moodle site and create a token for the user.
You need to create a service and add functions to it.

You need to enable **REST protocol** for token authentication or **webservice authentication method** for
username/password authentication.

<a href="https://docs.moodle.org/402/en/Using_web_services" target="_blank">Detailed documentation on moodle.org</a>

## Executing Web Services (Premium)

MDLCode can help you to prepare a command for executing a WebService and run it in the terminal.

You need to have a `curl` command installed in your system to actually execute a web service.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/executews/wizard.png">

MDLCode only supports REST protocol or webservice authentication method. Other protocols (such as SOAP) are
not currently supported in MDLCode.
