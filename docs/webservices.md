# Working with Web Services in MDLCode

## Identifying Web Services

When you spot an identifier highlighted in orange, it means that MDLCode has recognized a Moodle™ entity.

### Navigating to the Web Service Definition

You can either Ctrl+Click on an orange-highlighted web service name or right-click and select "Go to definition" from the context menu.

![Go to Definition](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/webservices/gotodefinition.png)

This will take you to the `db/services.php` file in the respective plugin where the web service is defined.

### Accessing Web Service Implementation

In the `db/services.php` file, you'll find a "Go to implementation" Code Lens positioned above the web service name. Click on it to access the web service's implementation.

![Go to Implementation](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/webservices/definition.png)

As you know, implementing a web service requires three functions. The provided Code Lenses enable easy navigation between these functions.

Next to the implementation function, you'll find "WS definition", "WS parameters", and "WS returns" Code Lenses. Click on them to access the respective definitions or methods.

![Implementation](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/webservices/implementation.png)

## Referencing Web Services (Premium)

Next to both the web service definition (in `db/services.php`) and the web service implementation function, you'll find the "X AJAX references" Code Lens. This feature directs you to the locations where the web service is called from JavaScript (JS) files.

Additionally, near the web service definition (in `db/services.php`), you'll find Code Lenses displaying a list of references from code and unittests.

If you see the "X references" Code Lens next to the web service implementation function, please note that this Code Lens is provided by your PHP extension, not MDLCode.

### Detecting Unused Web Services

MDLCode will report a problem if a web service is defined as AJAX but remains unused in JS files.

Please note that there can be false positives. You can use directives to suppress problem reporting or to inform MDLCode about existing references.

## Executing Web Services (Premium)

Refer to [Executing Web services](executews.md) for more information.

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
