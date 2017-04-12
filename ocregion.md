# Group Wholesale - Region region
	CURD oc.region support wholesale

## City [/api/wholesale/oc.region]
City (getlist city)

### Get city [GET]
Get city

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
					"id": 1,
					"name": "Hồ Chí Minh"
				},
				{
					"id": 2,
					"name": "Đồng Nai"
				},
				{
					"id": 3,
					"name": "Bình Dương"
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
			"parent_id": {
				"type": "interger",
				"mean": "ID region cha"
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

## District [/api/wholesale/oc.region/city/{id}]
District (getlist district)

### Get district [GET]
Get district

+ Parameters
	+ id: 1 (required) - Unique identifier for a oc region

+ Response 200 (application/json)
	+ Body
		```js
		{
			"count": 3,
			"results": [
				{
					"id": 4,
					"name": "Quận 7"
				},
				{
					"id": 5,
					"name": "Quận 1"
				},
				{
					"id": 6,
					"name": "Quận 3"
				}
			]
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

## Ward [/api/wholesale/oc.region/district/{id}]
Ward (getlist ward)

### Get ward detail [GET]
Get ward

+ Parameters
	+ id: 4 (required) - Unique identifier for a oc region

+ Response 200 (application/json)
	+ Body
		```js
		{
			"count": 1,
			"results": [
				{
					"id": 7,
					"name": "Tân Hưng"
				}
			]
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

## Detail [/api/wholesale/oc.region/view/{id}]
Region (detail)

### Get region detail [GET]
Get region

+ Parameters
	+ id: 4 (required) - Unique identifier for a oc region

+ Response 200 (application/json)
	+ Body
		```js
		{
			{
				"id": 4,
				"name": "Quận 7"
				"parent_id": 1
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
