# Group Wholesale - Source
	CURD utm.source support wholesale

## Source [/api/wholesale/utm.source]
Source (getlist)

### Get source [GET]
Get utm source title

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
					"name": "Doctor"
				},
				{
					"id": 1,
					"name": "Madam"
				},
				{
					"id": 2,
					"name": "Miss"
				},
				{
					"id": 3,
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

## Source [/api/wholesale/utm.source/{id}]
Source (getdetail)
### Get source detail [GET]
Get utm source detail

+ Parameters
	+ id: 4 (required) - Unique identifier for a res partner title

+ Response 200 (application/json)
	+ Body
		```js
		{
			"id": 4,
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
