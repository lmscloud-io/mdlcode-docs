# Working with Web Services in MDLCode

## Lookup web services

When you see an identifier highlighted in orange it means that MDLCode detected a Moodle
entity.

### Ctrl+Click to go to the web service definition

You can either Ctrl+Click on a web service name hightlighted in orange or
right click and select "Go to definition" from the context menu.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/webservices/gotodefinition.png">

This will take you to the `db/services.php` file in the respective plugin where the web service
is defined.

### Go to the web service implementation

When in the `db/services.php` file you can see "Go to implementation" Code Lens above the
web service name. Click on it to go to the implementation of the web service.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/webservices/definition.png">

As you know in order to implement a web service you need to implement three functions.
The Code Lenses will allow you to quickly navigate between them.

Next to the implementation function you can see "WS definition", "WS parameters" and
"WS returns" Code Lenses. Click on them to go to the definition or respective methods.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/webservices/implementation.png">

## Lookup web service references (Premium)

Next to both web service definition (in `db/services.php`) and web service implementation
function you can see the Code Lens "X AJAX references". This will take you to the places
where the web service is called from JS files.

Also next to the web service definition (in `db/services.php`) you can see the Code Lenses
with the list of references from code and from unittests.

If you see the "X references" Code Lens next to the web service implementation function,
note that this Code Lens is provided by your PHP extension and not by MDLCode.

### Identify unused web services

MDLCode will report a problem if a web service is defined as AJAX web service but is
never called from JS files.

Please note that there can be false positives. You can add [directives](directives.md) to
disable problem reporting or advise Mdlcode about existing references.
