# Group Wholesale - Category
	CURD res.partner.category support wholesale

## Category [/api/wholesale/res.partner.category]
Category (getlist)

### Get category [GET]
Get res partner category

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
					"parent_id": null,
					"id": 1,
					"name": "Khách hàng 1"
				},
				{
					"parent_id": 1,
					"id": 2,
					"name": "Khách hàng 2"
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
			"parent_id": {
				"type": "interger",
				"mean": "Category cha"
			},
			"name": {
				"type": "string",
				"mean": "Tên"
			},
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

## Category [/api/wholesale/res.partner.category/{id}]
Category (getdetail)

### Get category detail [GET]
Get res partner category detail

+ Parameters
	+ id: 2 (required) - Unique identifier for a res partner category

+ Response 200 (application/json)
	+ Body
		```js
		{
			"id": 2,
			"parent_id": 1,
			"name": "Khách hàng 2"
		}
		```
	+ Schema
		```js
		{
			"id": {
				"type": "interger",
				"mean": "ID"
			},
			"parent_id": {
				"type": "interger",
				"mean": "Category cha"
			},
			"name": {
				"type": "string",
				"mean": "Tên"
			},
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
