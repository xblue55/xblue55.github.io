# Group Wholesale - Product category
	CURD product.category support wholesale

## Product category [/api/wholesale/product.category]
Product category (getlist)

### Get product category [GET]
Get product category

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
					"display_name": "All",
					"name": "All",
					"parent_id": null,
					"property_valuation": "manual_periodic",
					"warehouse": [],
					"type": "normal",
					"id": 1
				},
				{
					"display_name": "All / Saleable",
					"name": "Saleable",
					"parent_id": 1,
					"property_valuation": "manual_periodic",
					"warehouse": [
						{
							"id": 1,
							"name": "My Company"
						},
						{
							"id": 2,
							"name": "home"
						}
					],
					"type": "normal",
					"id": 2
				}
			]
		}
		```
	+ Schema
		```js
		{
			"display_name": {
				"type": "string",
				"mean": "Tên hiển thị category"
			},
			"name": {
				"type": "string",
				"mean": "Tên category"
			},
			"parent_id": {
				"type": "interger",
				"mean": "ID category cha"
			},
			"property_valuation": {
				"type": "enum('manual_periodic', 'real_time')",
				"mean": "Inventory Valuation"
			},
			"warehouse": [
				{
					"id": {
						"type": "interger",
						"mean": "ID warehouse"
					},
					"name": {
						"type": "string",
						"mean": "Tên warehouse"
					}
				}
			],
			"type": {
				"type": "enum('view', 'normal')",
				"mean": "Kiễu category"
			},
			"id": {
				"type": "interger",
				"mean": "ID category"
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

## Product category [/api/wholesale/product.category/{id}]
Product category (getdetail)

### Get product category detail [GET]
Get product category detail

+ Parameters
	+ id: 2 (required) - Unique identifier for a product category

+ Response 200 (application/json)
	+ Body
		```js
		{
			"display_name": "All / Saleable",
			"name": "Saleable",
			"parent_id": 1,
			"property_valuation": "manual_periodic",
			"warehouse": [
				{
					"id": 1,
					"name": "My Company"
				},
				{
					"id": 2,
					"name": "home"
				}
			],
			"type": "normal",
			"id": 2
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
