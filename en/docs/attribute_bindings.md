# Attribute Bindings

Bindings can also be placed inside of attributes.

```html
<p class="{{ if _is_cool? }}cool{{ end }}">Text</p>
```

There are some special features provided to make elements work as "two way bindings":

```html
<input type="text" value="{{ _name }}" />
```

## CheckBoxes

In the example above, if ```_name``` changes, the field will update, and if the field is updated, ```_name``` will be changed:

```html
<input type="checkbox" checked="{{ _checked }}" />
```

If the value of a checked attribute is ```true```, the checkbox will be shown checked. If it's checked or unchecked, the value will be updated to ```true``` or ```false``` respectively.

## Radio Buttons

Radio buttons bind to a checked state as well, except instead of setting the value to true or false, they set it to a supplied field value.

```html
<input type="radio" checked="{{ _radio }}" value="one" />
<input type="radio" checked="{{ _radio }}" value="two" />
```

When a radio button is checked, whatever checked is bound to is set to the field's value.  When the checked binding value is changed, any radio buttons where the binding's value matches the fields value are checked.  NOTE: This seems to be the most useful behaviour for radio buttons.

## Select Boxes

Select boxes can be bound to a value (while not technically a DOM property, this is another convient behavior Volt adds).

```html
<select value="{{ _rating }}">
  <option value="1">*</option>
  <option value="2">**</option>
  <option value="3">***</option>
  <option value="4">****</option>
  <option value="5">*****</option>
</select>
```

When the selected option of the select above changes, ```_rating``` is changed to match.  When ```_rating``` is changed, the selected value is changed to the first option with a matching value.  If no matching values are found, the select box is unselected.

