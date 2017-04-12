# Group Wholesale - Quote template
	CURD sale.quote.template support wholesale

## Quote template [/api/wholesale/sale.quote.template]
Quote template (getlist)

### Get quote template [GET]
Get sale quote template

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
			"count": 1,
			"results": [
				{
					"quote_line": [
						{
							"product_id": 2,
							"product_uom_id": 1,
							"price_unit": 2,
							"product_uom_qty": 1,
							"id": 1,
							"name": "Sản phẩm mẫu"
						}
					],
					"id": 1,
					"name": "Default Template"
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
				"mean": "Quote template cha"
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

## Quote template [/api/wholesale/sale.quote.template/{id}]
Quote template (getdetail)

### Get quote template detail [GET]
Get sale quote template detail

+ Parameters
	+ id: 2 (required) - Unique identifier for a sale quote template

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
				"mean": "Quote template cha"
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
