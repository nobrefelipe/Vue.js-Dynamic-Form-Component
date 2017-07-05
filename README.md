# Vue.js Dynamic Form Component

> A Vue.js component for generating forms from a json map

On going project for personal and professional use, feel free to clone and improve it!

<a href="http://jsfiddle.net/v8rvnz6d/5/" target="_blank" title="See demo on Fiddle">Demo</a>

### Usage

Import the component then use it passing the form map as a prop:

`<dynamic-form :form="form"></dynamic-form>`


### Form Structure Sample

For now the `form.json` maps to input type text, submit, search, password, checkbox and radio. With the latest two able to be grouped.

```
[

    {"type": "text", "id": "text",  "value": "A text input", "label": "A text input"},

    {"type": "password", "id": "password", "value": "mypass", "label": "password"},

    {"type": "submit", "id": "submit", "value": "button", "label": ""},

    {"type": "search", "id": "search", "value": "A search input", "label": "A search input"},

    {"type": "checkbox", "id": "checkbox",  "value": "checkbox", "label": "A single checkbox"},

    {"type": "radio", "id": "radio",  "value": "radio", "label": "A single radio"},

    {
        "type": "select", "id": "select", "value":"", "label": "Dropdown",

        "label": "Dorpdown",

        "options": [

            {"name": "Option 1", "value": "Value1"},
            {"name": "Option 2", "value": "Value2"},
            {"name": "Option 3", "value": "Value3"}

        ]
    },

    {
        "type": "group",

        "elements": [

            { "type": "radio", "id": "radioA", "name": "radioGroup", "value": "radioA", "label": "Radio A"},
            { "type": "radio", "id": "radioB", "name": "radioGroup", "value": "radioB", "label": "Radio B"},
            { "type": "radio", "id": "radioC", "name": "radioGroup", "value": "radioC", "label": "Radio C"}

        ]
    },

    {
        "type": "group",

        "elements": [

            { "type": "checkbox", "id": "checkboxA", "name": "checkboxGroup", "value": "checkboxA", "label": "Checkbox A"},
            { "type": "checkbox", "id": "checkboxB", "name": "checkboxGroup", "value": "checkboxB", "label": "Checkbox B"},
            { "type": "checkbox", "id": "checkboxC", "name": "checkboxGroup", "value": "checkboxC", "label": "Checkbox C"}

        ]
    }
]
```


### TODO
 - Add hints and/or validation messages
 - Add submit callback option (?)
 - Style it (?)
