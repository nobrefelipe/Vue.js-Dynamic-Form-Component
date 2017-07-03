# Vue.js Dynamic Form Component

> A Vue.js component for generate forms from a json map

On going project for personal and professional use, feel free to clone and improve it!

Demo: http://jsfiddle.net/v8rvnz6d/

#### Usage

Import the component then use it passing the form map as a prop:

`<dynamic-form :form="form"></dynamic-form>`


#### Form Structure Sample

For now the form.json maps to input type text, submit, search, password, checkbox and radio. With the latest two able to be grouped.

```
[

    {"type": "text", "value": "A text input", "label": "A text input"},
    {"type": "submit", "value": "button", "label": ""},
    {"type": "search", "value": "A search input", "label": "A search input"},
    {"type": "checkbox", "value": "checkbox", "label": "A single checkbox"},
    {"type": "radio", "value": "radio", "label": "A single radio"},

    {
        "type": "group",
        "elements": [

            { "type": "radio", "name": "radio1", "value": "radioA", "label": "Radio A"},
            { "type": "radio", "name": "radio1", "value": "radioB", "label": "Radio B"},
            { "type": "radio", "name": "radio1", "value": "radioC", "label": "Radio C"}

        ]
    },

    {
        "type": "group",
        "elements": [

            { "type": "checkbox", "name": "checkbox1", "value": "checkboxA", "label": "Checkbox A"},
            { "type": "checkbox", "name": "checkbox1", "value": "checkboxB", "label": "Checkbox B"},
            { "type": "checkbox", "name": "checkbox1", "value": "checkboxC", "label": "Checkbox C"}

        ]
    }
]
```


#### TODO
 - Add Dropdown
 - Add hints and/or validation messages
 - Add submit callback option (?)
 - Style it (?)


## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```