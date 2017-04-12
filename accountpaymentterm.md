# Group Wholesale - Account invoice
	CURD account.invoice support wholesale

## Account invoice [/api/wholesale/account.invoice]
Account invoice (getlist)

### Get account invoice [GET]
Get account invoice

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
			"count": 3,
			"results": [
				{
					"note": "Payment term: 15 Days",
					"id": 2,
					"name": "15 Days"
				},
				{
					"note": "Payment term: 30 Net Days",
					"id": 3,
					"name": "30 Net Days"
				},
				{
					"note": "Payment term: Immediate Payment",
					"id": 1,
					"name": "Immediate Payment"
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
			"note": {
				"type": "string",
				"mean": "Ghi chú"
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

## Account invoice [/api/wholesale/account.invoice/{id}]
Account invoice (getdetail)

### Get account invoice detail [GET]
Get account invoice detail

+ Parameters
	+ id: 2 (required) - Unique identifier for a account invoice

+ Response 200 (application/json)
	+ Body
		```js
		{
			"note": "Payment term: 15 Days",
			"line_ids": [
				{
					"days": 15,
					"value": "balance",
					"option": "day_after_invoice_date"
				}
			],
			"id": 2,
			"name": "15 Days"
		}
		```
	+ Schema
		```js
		{
			"id": {
				"type": "interger",
				"mean": "ID"
			},
			"note": {
				"type": "string",
				"mean": "Ghi chú"
			},
			"line_ids": [
				{
					"days": {
						"type": "interger",
						"mean": "Number of Days"					
					},
					"value": {
						"type": "enum('balance', 'percent', 'fixed')",
						"mean": "Type"					
					},
					"option": {
						"type": "enum('day_after_invoice_date', 'day_after_invoice_date', 'last_day_following_month', 'last_day_current_month')",
						"mean": "Options"					
					}
				}
			]
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
