# Executing Web Services in MDLCode

* To execute a WebService, open the MDLCode Wizard and click "Execute WebService," or
* Click on "Execute WS" located next to the service definition or implementation

![Launch Execution](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/executews/launch.png)

## Setting Up WebServices

Before you can execute a WebService, you must configure the environment. Here's what you need to do:

1. Enable WebServices on your Moodle site.
2. Generate a token for the user.
3. Create a service and add necessary functions to it.
4. For authentication, you can either enable the **REST protocol** for token-based authentication or use the **webservice authentication method** for username/password-based authentication.

<a href="https://docs.moodle.org/402/en/Using_web_services" target="_blank">Learn more in detailed documentation on moodle.org</a>

## Executing Web Services (Premium)

MDLCode assists you in preparing a command for executing a WebService and subsequently running it in the terminal. However, please ensure you have the `curl` command installed on your system to perform the actual web service execution.

![MDLCode Wizard](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/executews/wizard.png)

MDLCode only supports the REST protocol and webservice authentication method. Please note that other protocols (such as SOAP) are not currently supported in MDLCode.

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
