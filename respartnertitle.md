# Group Wholesale - Title
	CURD res.partner.title support wholesale

## Title [/api/wholesale/res.partner.title]
Title (getlist)

### Get title [GET]
Get res partner title

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
					"id": 4,
					"shortcut": "Dr.",
					"name": "Doctor"
				},
				{
					"id": 1,
					"shortcut": "Mrs.",
					"name": "Madam"
				},
				{
					"id": 2,
					"shortcut": "Miss",
					"name": "Miss"
				},
				{
					"id": 3,
					"shortcut": "Mr.",
					"name": "Mister"
				},
				{
					"id": 5,
					"shortcut": "Prof.",
					"name": "Professor"
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
			"shortcut": {
				"type": "string",
				"mean": "Rút gọn"
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

## Title [/api/wholesale/res.partner.title/{id}]
Title (getdetail)
### Get title detail [GET]
Get res partner title detail

+ Parameters
	+ id: 4 (required) - Unique identifier for a res partner title

+ Response 200 (application/json)
	+ Body
		```js
		{
			"id": 4,
			"shortcut": "Dr.",
			"name": "Doctor"
		}
		```
	+ Schema
		```js
		{
			"id": {
				"type": "interger",
				"mean": "ID"
			},
			"shortcut": {
				"type": "string",
				"mean": "Rút gọn"
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
