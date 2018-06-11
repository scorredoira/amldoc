Example:

```json
{
    "id": "entities",
    "type": "amura.list",
    "columns": [
        "name"
    ],
    "options": {
        "headerVisible": false
    },
    "onClick": [
        {
            "target": "propertiesHeader",
            "command": "setTitle",
            "args": "${name}"
        },
        {
            "command": "load",
            "target": "properties",
            "args": {
                "url": "/amura/orm/properties.api",
                "args": {
                    "plugin": "${plugin}",
                    "entity": "${name}"
                }
            }
        }
    ]
}
```