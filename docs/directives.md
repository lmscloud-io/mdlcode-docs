# Directives in MDLCode

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/directives/directives_example.gif">

Sometimes MDLCode is unable to parse code and detect references to the entities
(string identifiers, templates, webservice names, database tables, etc).

Examples of such cases are:
- entity name is passed as a query string parameter, template variable or
  data- attribute in HTML
- entity name is received from calling a function that is located in a different file,
  especially when it is a class method that various plugins can override
- other situations when the entity name is dynamically generated
- there is a complicated chain of concatenations and referring to constants that
  are imported from different files, especially in JavaScript

This can result in false-positve reports that a string/template/webservice is not used.

Mdlcode will also raise a problem that entity can not be parsed.

If you want to reduce the number of false positives and help MDLCode to detect
references to the entities, you can add directives to the source code.

Directives can be added to the source code similar to eslint directives.

Only PHP and JS files support directives. Fullstop (.) can be added to the end of the
directives to comply with codechecker, MDLCode will ignore trailing fullstop.

## Disable

Disables problem reporting

Example: to disable problem reporting until the end of the file (In php files it will apply till the end of the function):
```php
// Mdlcode-disable cannot-parse-capability
```

Example: to disable problem reporting for one line:
```php
// Mdlcode-disable-next-line
get_string(optional_param('s', '', PARAM_TEXT));

'some code'; // Mdlcode-disable-line
```

## Uses

Adding "uses" directive will help MDLCode to navigate to all references.

It will also reduce the number of false positives reports about
missing references.

Example: for all entities except for strings:
```php
// Mdlcode uses: capability 'mod/forum:viewdiscussion'
```

Example: for strings you need to specify an array with an identifier and the component:
```php
// Mdlcode uses: string ['yes', 'moodle']
```

In PHP functions you can use also use "returns" directive that will be equivalent
to having "uses" directive before each return statement. In this case you only
need to specify the type of the entity and not the value.

Example: When the function returns a webservice name or an array of capabilities:

```php
// Mdlcode returns: webservice
// Mdlcode returns: [capability]
```

Example: When the function returns a string identifier from the component 'moodle':

```php
// Mdlcode returns: string 'moodle'
```

## Assume

Assume directives can be inserted before references to the variables which
values can not be detected automatically, especially when these variables
are used as string identifiers or components, templates, capabilities, etc.

Adding "assume" directive will reduce the number of false positive reports about
missing references.

"Assume" directives can 'replace' a variable with a value, range of values or
a list of pluginnames of a given type.

"Assume-optional" means that if the entity exists, the reference will be created
but if it does not, the "Missing entity" problem will not be reported.

Examples:

```php
// Mdlcode assume: $component fullpluginnames-availability
// Mdlcode assume-special: h5p-modforum-component-capability
// Mdlcode assume: $type->get_typename() pluginnames-repository

// Mdlcode assume: $capability ['viewcoursetools', 'viewsystemtools']
// Mdlcode assume: $this->criteriatype ['1','2','3','4','5','6','7','8','9']

// Mdlcode assume-optional: $instance->enrol pluginnames-enrol

// Mdlcode assume-optional-next-line: $component fullpluginnames-/^(?!mod$)/
// Mdlcode assume-optional-next-line: $component fullpluginnames-/^.*$/

// Mdlcode assume: $subpluginname subplugins-mod

// Mdlcode assume: $name namefields
// Mdlcode assume: $profile profilefields
```

## Advanced usage (for directive file only)

This functionality is not fully available yet, the documentation will be updated when it is ready.

### Callbacks

```php
// Mdlcode callback: mod PN_process_email function_exists($function)
// Mdlcode callback-next-line: ignore
// Mdlcode callback-next-line: report
// Mdlcode call-subject: (page|PAGE)->requires$
// Mdlcode call-subject: ^\$this$
// Mdlcode call-special: same-file-call-only
```

### Variant

```php
/**
 * @param string $capability {Mdlcode-variant-capability} The capability to assign
 * @return string {Mdlcode-variant-template}
 */
```

## Examples

Here are examples of using the directives for Moodle core:

https://github.com/moodle/moodle/compare/MOODLE_402_STABLE...lmscloud-io:moodle:mdlcode402

Note that this branch also includes directives like "callback", "variant" and "call-subject"
that are not available for the plugins yet.
