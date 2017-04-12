# Group Wholesale - Pricelist
	CURD product.pricelist support wholesale

## Pricelist [/api/wholesale/product.pricelist]
Pricelist (getlist)

### Get pricelist [GET]
Get pricelist

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
					"discount_policy": "with_discount",
					"id": 1,
					"item_ids": [
						{
							"fixed_price": 10,
							"percent_price": null,
							"name": "All Products",
							"date_end": "2017-04-11",
							"date_start": "2017-04-10",
							"compute_price": "fixed",
							"product_tmpl_id": null,
							"applied_on": "3_global",
							"min_quantity": 1,
							"categ_id": null,
							"product_id": null
						},
						{
							"fixed_price": null,
							"percent_price": 10,
							"name": "All Products",
							"date_end": "2017-04-11",
							"date_start": "2017-04-09",
							"compute_price": "percentage",
							"product_tmpl_id": null,
							"applied_on": "3_global",
							"min_quantity": 1,
							"categ_id": null,
							"product_id": null
						},
						{
							"fixed_price": null,
							"percent_price": null,
							"name": "All Products",
							"date_end": "2017-04-11",
							"date_start": "2017-04-08",
							"compute_price": "formula",
							"product_tmpl_id": null,
							"applied_on": "3_global",
							"min_quantity": 1,
							"categ_id": null,
							"product_id": null
						}
					],
					"name": "Public Pricelist"
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
			"discount_policy": {
				"type": "enum('with_discount', 'without_discount')",
				"mean": " Chính sách giảm giá"
			},
			"item_ids": [
				{
					"compute_price": {
						"type": "enum('fixed', 'percentage', 'formula')",
						"mean": "Cách tính giá tiền"					
					},
					"fixed_price": {
						"type": "float",
						"mean": "Số tiền được giảm"					
					},
					"percent_price": {
						"type": "float",
						"mean": "Phần trăm giảm giá"					
					},
					"min_quantity": {
						"type": "interger",
						"mean": "Số lượng tối thiểu"					
					},
					"applied_on": {
						"type": "enum('3_global', '2_product_category', '1_product', '0_product_variant')",
						"mean": "Áp dụng cho loại được chọn"					
					},
					"date_start": {
						"type": "date",
						"mean": "Ngày bắt đầu"
					},
					"date_end": {
						"type": "date",
						"mean": "Ngày kết thúc"					
					},
					"categ_id": {
						"type": "interger",
						"mean": "Danh mục sản phẩm"
					},
					"product_tmpl_id": {
						"type": "interger",
						"mean": "Sản phẩm"
					},
					"product_id": {
						"type": "interger",
						"mean": "Sản phẩm"
					},
					"name": {
						"type": "string",
						"mean": "Tên"
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

## Pricelist [/api/wholesale/product.pricelist/{id}]
Pricelist (getdetail)

### Get pricelist detail [GET]
Get pricelist detail

+ Parameters
	+ id: 1 (required) - Unique identifier for a pricelist

+ Response 200 (application/json)
	+ Body
		```js
		{
			"discount_policy": "with_discount",
			"id": 1,
			"item_ids": [
				{
					"fixed_price": 10,
					"percent_price": null,
					"name": "All Products",
					"date_end": "2017-04-11",
					"date_start": "2017-04-10",
					"compute_price": "fixed",
					"product_tmpl_id": null,
					"applied_on": "3_global",
					"min_quantity": 1,
					"categ_id": null,
					"product_id": null
				},
				{
					"fixed_price": null,
					"percent_price": 10,
					"name": "All Products",
					"date_end": "2017-04-11",
					"date_start": "2017-04-09",
					"compute_price": "percentage",
					"product_tmpl_id": null,
					"applied_on": "3_global",
					"min_quantity": 1,
					"categ_id": null,
					"product_id": null
				},
				{
					"fixed_price": null,
					"percent_price": null,
					"name": "All Products",
					"date_end": "2017-04-11",
					"date_start": "2017-04-08",
					"compute_price": "formula",
					"product_tmpl_id": null,
					"applied_on": "3_global",
					"min_quantity": 1,
					"categ_id": null,
					"product_id": null
				}
			],
			"name": "Public Pricelist"
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
