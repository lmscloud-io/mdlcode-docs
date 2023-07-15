# Working with form elements in MDLCode

MDLCode makes it easier for you to add elements to the moodleforms.

## Lookup form elements

When you see an identifier highlighted in orange it means that MDLCode detected a Moodle
entity.

### Ctrl+Click to go to the form element class

Wherever you call `$mform->addElement()` or `$mform->createElement()` the first parameter
will represent a name of the form element. The other parameters must be the same as in
the constructor of this form element class. It is hard to remember all parameters
for all form element classes, so MDLCode will help you with that.

You can either Ctrl+Click on a form element name hightlighted in orange or
right click and select "Go to definition" from the context menu.

This will take you to the class responsible for this form element. In this class you
can find the constructor and see what parameters it accepts.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/formelements/gotodefinition.png">

### Detect references to non-existing form elements

If you made a mistake in the form element name, MDLCode will detect it and report as a problem.

## Lookup form element references (Premium)

When you define your own form element you will need to register it, for example:

```php
MoodleQuickForm::registerElementType('submit', "$CFG->libdir/form/submit.php", 'MoodleQuickForm_submit');
```

Above this line you will see the Code Lenses with the list of references to this form element
from code and from unittests.

For all core form elements you can find these references in the end of the file `lib/formslib.php`.

<img src="https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/formelements/references.png">
