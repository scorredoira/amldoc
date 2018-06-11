## Timetable

Ejemplo:

```json
{
    "type": "tile",
    "children": [
        {
            "type": "amura.timetable",
            "id": "timetable",
            "posURL": "/views/public/apps/main/pos",
            "pixelsPerMin": 5,
            "hourColumnInterval": 10,
            "columns": [
                {
                    "idResourceType": 1,
                    "idResource": 1,
                    "width": 40
                },
                {
                    "idResourceType": 1,
                    "idResource": 2,
                    "width": 40
                },
                {
                    "idResourceType": 2
                },
                {
                    "idResourceType": 3
                }
            ]
        }
    ]
}
```