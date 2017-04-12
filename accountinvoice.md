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
			"count": 1,
			"results": [
				 {
					"amount_tax": 72727.27,
					"date_due": null,
					"amount_untaxed": 727272.73,
					"name": null,
					"user_id": {
						"id": 25,
						"name": "Phạm Đình Công"
					},
					"discount_type_id": null,
					"number": null,
					"account_id": {
						"display_name": "131 Phải thu của khách hàng",
						"id": 7
					},
					"residual": null,
					"date_invoice": null,
					"journal_id": {
						"display_name": "Customer Invoices (VND)",
						"id": 1
					},
					"state": "draft",
					"invoice_line_ids": [
						{
							"name": "CF Phin SỐ 1-DARK CHOCOLATE- 1000GR",
							"discount_type": "percent",
							"price_unit": 160000,
							"price_subtotal": 727272.73,
							"account_id": {
								"display_name": "5111 Doanh thu bán hàng hóa",
								"id": 118
							},
							"discount": null,
							"product_id": {
								"barcode": "8110023300001",
								"categ_id": {
									"id": 8,
									"name": "PHIN"
								},
								"id": 66,
								"name": "Cà phê Phin số 1 - Dark Chocolate - Gói 1kg"
							},
							"id": 49091,
							"quantity": 5
						}
					],
					"discount_value": null,
					"payment_term_id": 1,
					"partner_id": {
						"city": "Quận 2",
						"id": 4200,
						"name": "CF Thảo Mộc - Nguyễn Xiển"
					},
					"id": 17988,
					"fiscal_position_id": {
						"id": null,
						"name": null
					},
					"amount_total": 800000
				}
			]
		}
		```
	+ Schema
		```js
		{
			"count": 1,
			"results": [
				 {
					"amount_tax": {
						"type": "float",
						"mean": "Giá tiền tổng"
					},
					"date_due": {
						"type": "date",
						"mean": "Due date"
					},
					"amount_untaxed": {
						"type": "float",
						"mean": "Giá tiền chưa thuế"
					},
					"name": {
						"type": "string",
						"mean": "Tên"
					},
					"user_id": {
						"id": {
							"type": "interger",
							"mean": "ID nhân viên bán hàng"
						},
						"name": {
							"type": "string",
							"mean": "Tên nhân viên bán hàng"
						}
					},
					"discount_type_id": {
						"type": "interger",
						"mean": "Loại giảm giá"
					},
					"number": {
						"type": "",
						"mean": ""
					},
					"account_id": {
						"display_name": {
							"type": "string",
							"mean": "Tên Account"
						},
						"id": {
							"type": "interger",
							"mean": "ID Account"
						}
					},
					"residual": {
						"type": "",
						"mean": ""
					},
					"date_invoice": {
						"type": "date",
						"mean": ""
					},
					"journal_id": {
						"display_name": {
							"type": "interger",
							"mean": "Tên journal"
						},
						"id": {
							"type": "interger",
							"mean": "ID journal"
						}
					},
					"state": {
						"type": "enum('draft', 'proforma', 'proforma2', 'open', 'paid', 'cancel')",
						"mean": "Trạng thái"
					},
					"invoice_line_ids": [
						{
							"name": {
								"type": "string",
								"mean": "Tên invoice line"
							},
							"discount_type": {
								"type": "string",
								"mean": "Loại giảm giá"
							},
							"price_unit": {
								"type": "float",
								"mean": "Đơn g"
							},
							"price_subtotal": {
								"type": "float",
								"mean": "Tổng tạm tính"
							},
							"account_id": {iá
								"display_name": {
									"type": "string",
									"mean": "Tên account"
								},
								"id": {
									"type": "interger",
									"mean": "ID account"
								}
							},
							"discount": {
								"type": "float",
								"mean": "Giảm giá"
							},
							"product_id": {
								"barcode": {
									"type": "string",
									"mean": "barcode sản phẩm"
								},
								"categ_id": {
									"id": {
										"type": "interger",
										"mean": "ID danh mục sản phẩm"
									},
									"name": {
										"type": "string",
										"mean": "Tên danh mục sản phẩm"
									}
								},
								"id": {
									"type": "interger",
									"mean": "ID sản phẩm"
								},
								"name": {
									"type": "string",
									"mean": "Tên sản phẩm"
								}
							},
							"id": {
								"type": "interger",
								"mean": "ID invoice line"
							},
							"quantity": {
								"type": "interger",
								"mean": "Số lượng sản phẩm"
							}
						}
					],
					"discount_value": {
						"type": "float",
						"mean": "Giá trị giảm giá"
					},
					"payment_term_id": {
						"type": "interger",
						"mean": ""
					},
					"partner_id": {
						"city": {
							"type": "string",
							"mean": "Thành phố partner"
						},
						"id": {
							"type": "interger",
							"mean": "ID partner"
						},
						"name": {
							"type": "string",
							"mean": "Tên partner"
						}
					},
					"id": {
						"type": "interger",
						"mean": "ID account invoice"
					},
					"fiscal_position_id": {
						"id": {
							"type": "interger",
							"mean": ""
						},
						"name": {
							"type": "string",
							"mean": ""
						}
					},
					"amount_total": {
						"type": "float",
						"mean": "Giá tiền tổng"
					}
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

## Account invoice [/api/wholesale/account.invoice/{id}]
Account invoice (getdetail)

### Get account invoice detail [GET]
Get account invoice detail

+ Parameters
	+ id: 3 (required) - Unique identifier for a account invoice

+ Response 200 (application/json)
	+ Body
		```js
		{
			"amount_tax": 72727.27,
			"date_due": null,
			"amount_untaxed": 727272.73,
			"name": null,
			"user_id": {
				"id": 25,
				"name": "Phạm Đình Công"
			},
			"discount_type_id": null,
			"number": null,
			"account_id": {
				"display_name": "131 Phải thu của khách hàng",
				"id": 7
			},
			"residual": null,
			"date_invoice": null,
			"journal_id": {
				"display_name": "Customer Invoices (VND)",
				"id": 1
			},
			"state": "draft",
			"invoice_line_ids": [
				{
					"name": "CF Phin SỐ 1-DARK CHOCOLATE- 1000GR",
					"discount_type": "percent",
					"price_unit": 160000,
					"price_subtotal": 727272.73,
					"account_id": {
						"display_name": "5111 Doanh thu bán hàng hóa",
						"id": 118
					},
					"discount": null,
					"product_id": {
						"barcode": "8110023300001",
						"categ_id": {
							"id": 8,
							"name": "PHIN"
						},
						"id": 66,
						"name": "Cà phê Phin số 1 - Dark Chocolate - Gói 1kg"
					},
					"id": 49091,
					"quantity": 5
				}
			],
			"discount_value": null,
			"payment_term_id": 1,
			"partner_id": {
				"city": "Quận 2",
				"id": 4200,
				"name": "CF Thảo Mộc - Nguyễn Xiển"
			},
			"id": 17988,
			"fiscal_position_id": {
				"id": null,
				"name": null
			},
			"amount_total": 800000
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
