# Working with Form Elements in MDLCode

MDLCode simplifies the process of adding elements to moodleforms.

## Identifying Form Elements

Whenever you encounter an identifier highlighted in orange, it signifies that MDLCode has recognized a Moodle™ entity.

### Navigating to the Form Element Class

In instances where you call `$mform->addElement()` or `$mform->createElement()`, the first parameter refers to the form element's name. The remaining parameters should match those within the constructor of the corresponding form element class.
With MDLCode you no longer need to remember all different
parameters for different elements.

You can either Ctrl+Click on an orange-highlighted form element name or right-click and select "Go to definition" from the context menu. This action will take you to the class responsible for the form element. Within this class, you can inspect the constructor and its accepted parameters.

![Go to Definition](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/formelements/gotodefinition.png)

### Detecting References to Non-Existing Form Elements

Should you make an error in the form element's name, MDLCode will promptly identify it and flag it as a problem.

## Referencing Form Elements (Premium)

When creating your custom form element, it's essential to register it. For instance:

```php
MoodleQuickForm::registerElementType('submit', "$CFG->libdir/form/submit.php", 'MoodleQuickForm_submit');
```

Just above this line, you'll spot Code Lenses that present references to this form element within the code and unit tests.

For all core form elements, you can locate these references at the end of the `lib/formslib.php` file.

![References](https://raw.githubusercontent.com/lmscloud-io/mdlcode-docs/main/docs/media/formelements/references.png)

---

To explore other MDLCode features, refer to the [main documentation page](README.md).
