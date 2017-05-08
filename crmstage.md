# Group Wholesale - State
    CURD crm.stage support wholesale

## Source [/api/wholesale/crm.stage]
Source (getlist)

### Get Stage [GET]
Get crm.stage

+ Request
    ```js
    {
        "filters": "[('some_field_1', '=', some_value_1), ('some_field_2', '!=', some_value_2)]",
        "offset": "interger",
        "limit": "interger",
        "order": "list_of_fields"
    }
    ```

+ Response 200 (application/json)
    + Body
        ```js
        {
            "count": 5,
            "results": [
                {
                  "legend_priority": null,
                  "team_id": null,
                  "id": 1,
                  "probability": 10,
                  "name": "New"
                },
                {
                  "legend_priority": null,
                  "team_id": null,
                  "id": 2,
                  "probability": 30,
                  "name": "Qualified"
                },
                {
                  "legend_priority": null,
                  "team_id": null,
                  "id": 3,
                  "probability": 70,
                  "name": "Proposition"
                },
                {
                  "legend_priority": null,
                  "team_id": null,
                  "id": 4,
                  "probability": 100,
                  "name": "Won"
                },
                {
                  "legend_priority": null,
                  "team_id": null,
                  "id": 5,
                  "probability": 10,
                  "name": "2123123"
                }
            ]
        }
        ```
    + Schema
        ```js
        {
            "id": {
                "type": "interger",
                "mean": "ID"
            },
            "name": {
                "type": "string",
                "mean": "Tên"
            },
            "probability": {
                "type": "integer",
                "mean": "Tỷ lệ thành công"
            },
            "team_id": {
                "type" : "integer",
                "mean": "Team dùng stage này"
            }
        }
        ```

+ Response 500 (application/json)

    ```js
    {
        "error_descrip": "Message",
        "error": "message_code"
    }
    ```

+ Response 401 (application/json)

    ```js
    {
        "error_descrip": "Message",
        "error": "message_code"
    }
    ```

+ Response 400 (application/json)

    ```js
    {
        "error_descrip": "Message",
        "error": "message_code"
    }
    ```

## Source [/api/wholesale/crm.stage/{id}]
Source (getdetail)
### Get Stage detail [GET]
Get Crm Stage detail

+ Parameters
    + id: 4 (required) - Unique identifier for a res partner title

+ Response 200 (application/json)
    + Body
        ```js
        {
            "legend_priority": null,
            "team_id": null,
            "id": 1,
            "probability": 10,
            "name": "New"
        },
        ```
    + Schema
        ```js
         {
            "id": {
                "type": "interger",
                "mean": "ID"
            },
            "name": {
                "type": "string",
                "mean": "Tên"
            },
            "probability": {
                "type": "integer",
                "mean": "Tỷ lệ thành công"
            },
            "team_id": {
                "type" : "integer",
                "mean": "Team dùng stage này"
            }
        }
        ```

+ Response 500 (application/json)

    ```js
    {
        "error_descrip": "Message",
        "error": "message_code"
    }
    ```

+ Response 401 (application/json)

    ```js
    {
        "error_descrip": "Message",
        "error": "message_code"
    }
    ```

+ Response 400 (application/json)

    ```js
    {
        "error_descrip": "Message",
        "error": "message_code"
    }
    ```

## Source [/api/wholesale/crm.stage/fromteamid/{id}]
Source (getdetail)
### Get stage detail [GET]
Get crm stage detail from leadid

+ Parameters
    + id: 4 (required) - Unique identifier for a res partner title

+ Response 200 (application/json)
    + Body
        ```js
        {
            "count": 5,
            "results": [
                {
                  "legend_priority": null,
                  "team_id": 1,
                  "id": 1,
                  "probability": 10,
                  "name": "New"
                },
                {
                  "legend_priority": null,
                  "team_id": 1,
                  "id": 2,
                  "probability": 30,
                  "name": "Qualified"
                },
                {
                  "legend_priority": null,
                  "team_id": 1,
                  "id": 3,
                  "probability": 70,
                  "name": "Proposition"
                },
                {
                  "legend_priority": null,
                  "team_id": 1,
                  "id": 4,
                  "probability": 100,
                  "name": "Won"
                },
                {
                  "legend_priority": null,
                  "team_id": 1,
                  "id": 5,
                  "probability": 10,
                  "name": "2123123"
                }
            ]
        }
        ```
    + Schema
        ```js
         {
            "id": {
                "type": "interger",
                "mean": "ID"
            },
            "name": {
                "type": "string",
                "mean": "Tên"
            },
            "probability": {
                "type": "integer",
                "mean": "Tỷ lệ thành công"
            },
            "team_id": {
                "type" : "integer",
                "mean": "Team dùng stage này"
            }
        }
        ```

+ Response 500 (application/json)

    ```js
    {
        "error_descrip": "Message",
        "error": "message_code"
    }
    ```

+ Response 401 (application/json)

    ```js
    {
        "error_descrip": "Message",
        "error": "message_code"
    }
    ```

+ Response 400 (application/json)

    ```js
    {
        "error_descrip": "Message",
        "error": "message_code"
    }
    ```
