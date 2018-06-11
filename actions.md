# Acciones

Las acciónes pueden ser objetos individuales o arrays indistintamente:

Un ejemplo básico:

```json
"onClick": {
    "target": "list",
    "command": "refresh"
}
```

Múltiples acciones:

```json
"onClick": [
    {
        "target": "list",
        "command": "refresh"
    },
    {
        "target": "list2",
        "command": "refresh"
    }
]
```



Example setting a property of an object:
```json
{
    "target": "detail",
    "command": "load",
    "args": {
        "entity": "amura.billing.product",
        "id": "${0}"
    }
}
```

## targets by tag

Given the following widget:

```javascript
{
    type: "amura.cashregister",
    tags: ["listenToDate"]
}
```

It can be referenced by **targetTag**

```javascript
onClick: {
    command: "refresh",
    targetTag: "listenToDate",
    args: { date: "${@}" }
}
```



## argsSource

Es posible leer los argumentos de una acción de otro widget.

```json
{
    "target": "detail",
    "command": "create",
    "argsSource": {
        "source": "products",
        "function": "getSelectedRow"
    },
    "args": {
        "entity": "amura.billing.price",
        "model": {
            "idProduct": "${0}"
        }
    }
}
```


## readArgs syntax

- **${@}** the whole model.
- **${0}** the 0 index of an array.
- **${foo}** the "foo" property of an object.


Objects and arrays as sources are permitted. For example:

```json
{ "entity": "${0}", "property": "${2}" }
```
Or
```json
[ "foo", "${bar}" ]
```


## onSuccess

Se ejecuta inmediatamente de pasar con éxito la acción:

```json
"onClick": [
    {
        "target": "detail",
        "command": "delete",
        "onSuccess": {
            "target": "list",
            "command": "refresh"
        }
    }
]
```

## callback

Se le pasa al target junto con la acción. El widget debe implementar la opción de callback:

```json
"onClick": {
    "target": "detail",
    "command": "copy",
    "callback": [
        {
            "target": "products",
            "command": "refresh"
        },
        {
            "target": "prices",
            "command": "refresh"
        }
    ]
}
```
