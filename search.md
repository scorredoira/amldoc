## Buscador avanzado

![Search](images/search.png)

Se puede especificar una entidad o las propiedades individuales

```json
{
    "label": "@@Filtrar",
    "type": "amura.search",
    "entity": "amura.billing.product",
    "container": "search",
    "onChanged": {
        "target": "products",
        "command": "refresh"
    }
}
```