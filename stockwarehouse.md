# Group Wholesale - Warehouse
	CURD warehouse support wholesale

## Warehouse [/api/wholesale/warehouse]
Warehouse (getlist)

### Get warehouse [GET]
Get warehouse

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
			"count": 2,
			"results": [
				{
					"code": "WH",
					"partner_id": 1,
					"id": 1,
					"name": "My Company"
				},
				{
					"code": "home",
					"partner_id": 8,
					"id": 2,
					"name": "home"
				}
			]
		}
		```
	+ Schema
		```js
		{
			"code": {
				"type": "string",
				"mean": "Tên rút gọn category"
			},
			"name": {
				"type": "string",
				"mean": "Tên warehouse"
			},
			"partner_id": {
				"type": "interger",
				"mean": "ID partner"
			},
			"id": {
				"type": "interger",
				"mean": "ID warehouse"
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

## Warehouse [/api/wholesale/warehouse/{id}]
Warehouse (getdetail)

### Get warehouse detail [GET]
Get warehouse detail

+ Parameters
	+ id: 2 (required) - Unique identifier for a warehouse

+ Response 200 (application/json)
	+ Body
		```js
		{
			"code": "WH",
			"partner_id": 1,
			"id": 1,
			"name": "My Company"
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
