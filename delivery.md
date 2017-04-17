# Group Wholesale - Delivery
    CURD Delivery support wholesale

## Delivery [/api/wholesale/stock.picking]
Delivery (getlist)

### Get delivery [GET]
Get stock picking

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
                    "origin": "PO00002",
                    "pack_operation_product_ids": [
                        {
                            "qty_done": null,
                            "product_id": 2,
                            "product_unit_price": 10,
                            "product_qty": 1
                        }
                    ],
                    "apply_discount": null,
                    "delivery_fee": null,
                    "customer_reference": null,
                    "note_stock_picking": null,
                    "duration_time": "0.0 mins",
                    "source_way": null,
                    "partner_id": 7,
                    "id": 45,
                    "postage_delivery_fee": null,
                    "amount_untaxed": 10,
                    "stock_tranfer_date": "2017-04-11 02:46:56",
                    "location_id": 8,
                    "postage_delivery": null,
                    "discount_type_id": null,
                    "amount_tax": null,
                    "state": "assigned",
                    "picking_type_code": "incoming",
                    "pricelist_id": null,
                    "delivery_service": "internal",
                    "move_lines": [
                    {
                        "price_total": 10,
                        "price_tax": null,
                        "product_id": 2,
                        "discount_type": "percent",
                        "price_unit": 10,
                        "product_uom_qty": 1,
                        "price_subtotal": 10,
                        "discount": null,
                        "state": "assigned",
                        "tax_id": []
                    }
                    ],
                    "start_time": null,
                    "destination_way": null,
                    "min_date": "2017-04-11 02:46:56",
                    "discount_account": null,
                    "amount_after_discount": 10,
                    "google_map": null,
                    "warehouse_destination_name": "My Company",
                    "delivery_status": "pending_delivery",
                    "warehouse_name": null,
                    "postage_total": null,
                    "amount_total": 10,
                    "collaborators": null,
                    "name": "WH/IN/00002",
                    "total_way": null,
                    "stock_outin_date": "2017-04-11 02:49:12",
                    "forecast_time": null,
                    "customer_type": null,
                    "location_dest_id": 15,
                    "end_time": null,
                    "end_point": {
                        "lat": null,
                        "lng": null,
                        "id": null,
                        "name": null
                    },
                    "discount_value": null,
                    "start_point": {
                        "lat": null,
                        "lng": null,
                        "id": null,
                        "name": null
                    }
                }
            ]
        }
        ```

    + Schema
        ```js
        {
            "count": {
                "type": "interger",
                "mean": "Số kết quả tìm được"
            },
            "results": [
                {
                    "origin": {
                        "type": "string",
                        "mean": "Mã truy xuất SO hoặc PO"
                    },
                    "pack_operation_product_ids": [
                        {
                            "qty_done": {
                                "type": "interger",
                                "mean": "Số lượng sản phẩm đã giao"
                            },
                            "product_id": {
                                "type": "interger",
                                "mean": "Sản phẩm"
                            },
                            "product_unit_price": {
                                "type": "float",
                                "mean": "Giá sản phẩm"
                            },
                            "product_qty": {
                                "type": "interger",
                                "mean": "Số lượng sản phẩm phải giao"
                            },
                        }
                    ],
                    "apply_discount": {
                        "type": "boolean",
                        "mean": "Áp dụng giảm giá"
                    },
                    "delivery_fee": {
                                "type": "float",
                                "mean": "Phí giao hàng"
                            },
                    "customer_reference": {
                                "type": "string",
                                "mean": "Mã truy xuất khách hàng"
                            },
                    "note_stock_picking": {
                                "type": "string",
                                "mean": "Ghi chú giao hàng"
                            },
                    "duration_time": {
                                "type": "string",
                                "mean": "Thời gian thực tế"
                            },
                    "source_way": {
                                "type": "float",
                                "mean": "Quãng đường đi"
                            },
                    "partner_id": {
                                "type": "string",
                                "mean": "Khách hàng"
                            },
                    "id": {
                                "type": "interger,
                                "mean": "Mã DO"
                            },
                    "postage_delivery_fee": {
                                "type": "string",
                                "mean": "Phụ phí giao hàng"
                            },
                    "amount_untaxed": {
                                "type": "float",
                                "mean": "Tổng tiền chưa thuế"
                            },
                    "stock_tranfer_date": {
                                "type": "datetime",
                                "mean": "Thời gian giao hàng"
                            },
                    "location_id": {
                                "type": "interger",
                                "mean": "Source Location Zone"
                            },
                    "postage_delivery": {
                                "type": "float",
                                "mean": "Phí giao hàng"
                            },
                    "discount_type_id": {
                                "type": "float",
                                "mean": "Phí giao hàng"
                            },
                    "amount_tax": {
                        "type": "float",
                        "mean": "Tổng thuế"
                    },
                    "state": {
                        "type": "enum('draft', 'cancel', 'waiting', 'confirmed', 'partially_available', 'assigned', 'done')",
                        "mean": "Trạng thái DO"
                    },
                    "picking_type_code": {
                        "type": "enum('incoming', 'outgoing', 'internal')",
                        "mean": "Loại DO"
                    },
                    "pricelist_id": {
                        "type": "interger",
                        "mean": "Pricelist"
                    },
                    "delivery_service": {
                        "type": "enum('internal', 'collaborators', 'partner')",
                        "mean": "Dịch vụ giao hàng"
                    },
                    "move_lines": [
                    {
                        "price_total": 10,
                        "price_tax": null,
                        "product_id": 2,
                        "discount_type": "percent",
                        "price_unit": 10,
                        "product_uom_qty": 1,
                        "price_subtotal": 10,
                        "discount": null,
                        "state": "assigned",
                        "tax_id": []
                    }
                    ],
                    "start_time": {
                        "type": "float",
                        "mean": "Thời gian xuất phát"
                    },
                    "destination_way": {
                        "type": "float",
                        "mean": "Quảng đường về"
                    },
                    "min_date": {
                        "type": "Datetime",
                        "mean": "Scheduled Date"
                    },
                    "discount_account": {
				"type": "interger",
				"mean": "Discount account"
			},
                    "amount_after_discount": {
                        "type": "float",
                        "mean": "Giá sau khi giảm giá"
                    },
                    "google_map": {
                        "type": "string",
                        "mean": "Link google map"
                    },
                    "warehouse_destination_name": {
				"type": "",
				"mean": ""
			},
                    "delivery_status": {
                        "type": "enum('pending_delivery', 'delivering', 'delivered')",
                        "mean": "Trạng thái giao hàng"
                    },
                    "warehouse_name": null,
                    "postage_total": null,
                    "amount_total": {
                        "type": "float",
                        "mean": "Giá tiền tổng"
                    },
                    "collaborators": {
                        "type": "interger",
                        "mean": "Nhân viên giao hàng"
                    },
                    "name": {
                        "type": "string",
                        "mean": "Tên DO"
                    },
                    "total_way": {
                        "type": "float",
                        "mean": "Tổng quảng đường"
                    },
                    "stock_outin_date": {
                        "type": "Datetime",
                        "mean": "Thời gian xuất/nhập kho"
                    },
                    "forecast_time": {
                        "type": "string",
                        "mean": "Thời gian dự đoán"
                    },
                    "customer_type": {
                        "type": "enum('cash', 'debts', 'deposit', 'internal')",
                        "mean": "Loại khách hàng"
                    },
                    "location_dest_id": {
				"type": "interger",
				"mean": "Destination location zone"
			},
                    "end_time": {
                        "type": "float",
                        "mean": "Thời gian trở về"
                    },
                    "end_point": {
                        "lat": {
				"type": "float",
				"mean": "Latitute"
			},
                        "lng": {
				"type": "float",
				"mean": "Longitute"
			},
                        "id": {
				"type": "interger",
				"mean": "ID địa chỉ"
			},
                        "name": {
				"type": "string",
				"mean": "Địa chỉ"
			}
                    },
                    "discount_value": {
				"type": "float",
				"mean": "Giảm giá"
			},
                    "start_point": {
                        "lat": {
				"type": "float",
				"mean": "Latitute"
			},
                        "lng": {
				"type": "float",
				"mean": "Longitute"
			},
                        "id": {
				"type": "interger",
				"mean": "ID địa chỉ"
			},
                        "name": {
				"type": "string",
				"mean": "Địa chỉ"
			}
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

## Delivery [/api/wholesale/stock.picking/{id}]
Delivery (detail)

### Get delivery detail [GET]
Get stock picking detail
    
+ Parameters
    + id: 1 (required) - Unique identifier for a delivery

+ Response 200 (application/json)
    + Body
        ```js
        {
        	"origin": "PO00002",
            "pack_operation_product_ids": [
                {
                    "qty_done": null,
                    "product_id": 2,
                    "product_unit_price": 10,
                    "product_qty": 1
                }
            ],
            "apply_discount": null,
            "delivery_fee": null,
            "customer_reference": null,
            "note_stock_picking": null,
            "duration_time": "0.0 mins",
            "source_way": null,
            "partner_id": 7,
            "id": 45,
            "postage_delivery_fee": null,
            "amount_untaxed": 10,
            "stock_tranfer_date": "2017-04-11 02:46:56",
            "location_id": 8,
            "postage_delivery": null,
            "discount_type_id": null,
            "amount_tax": null,
            "state": "assigned",
            "picking_type_code": "incoming",
            "pricelist_id": null,
            "delivery_service": "internal",
            "move_lines": [
            {
                "price_total": 10,
                "price_tax": null,
                "product_id": 2,
                "discount_type": "percent",
                "price_unit": 10,
                "product_uom_qty": 1,
                "price_subtotal": 10,
                "discount": null,
                "state": "assigned",
                "tax_id": []
            }
            ],
            "start_time": null,
            "destination_way": null,
            "min_date": "2017-04-11 02:46:56",
            "discount_account": null,
            "amount_after_discount": 10,
            "google_map": null,
            "warehouse_destination_name": "My Company",
            "delivery_status": "pending_delivery",
            "warehouse_name": null,
            "postage_total": null,
            "amount_total": 10,
            "collaborators": null,
            "name": "WH/IN/00002",
            "total_way": null,
            "stock_outin_date": "2017-04-11 02:49:12",
            "forecast_time": null,
            "customer_type": null,
            "location_dest_id": 15,
            "end_time": null,
            "end_point": {
                "lat": null,
                "lng": null,
                "id": null,
                "name": null
            },
            "discount_value": null,
            "start_point": {
                "lat": null,
                "lng": null,
                "id": null,
                "name": null
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

## Delivery [/api/wholesale/stock.picking/from.sale.order/{id}]
Delivery from SO

### Get delivery detail from sale order [GET]
Get stock picking detail from order
    
+ Parameters
    + id: 1 (required) - Unique identifier for a sale order

+ Response 200 (application/json)
    + Body
        ```js
		[
			{
			    "origin": "PO00002",
			    "pack_operation_product_ids": [
			        {
			            "qty_done": null,
			            "product_id": 2,
			            "product_unit_price": 10,
			            "product_qty": 1
			        }
			    ],
			    "apply_discount": null,
			    "delivery_fee": null,
			    "customer_reference": null,
			    "note_stock_picking": null,
			    "duration_time": "0.0 mins",
			    "source_way": null,
			    "partner_id": 7,
			    "id": 45,
			    "postage_delivery_fee": null,
			    "amount_untaxed": 10,
			    "stock_tranfer_date": "2017-04-11 02:46:56",
			    "location_id": 8,
			    "postage_delivery": null,
			    "discount_type_id": null,
			    "amount_tax": null,
			    "state": "assigned",
			    "picking_type_code": "incoming",
			    "pricelist_id": null,
			    "delivery_service": "internal",
			    "move_lines": [
			    {
			        "price_total": 10,
			        "price_tax": null,
			        "product_id": 2,
			        "discount_type": "percent",
			        "price_unit": 10,
			        "product_uom_qty": 1,
			        "price_subtotal": 10,
			        "discount": null,
			        "state": "assigned",
			        "tax_id": []
			    }
			    ],
			    "start_time": null,
			    "destination_way": null,
			    "min_date": "2017-04-11 02:46:56",
			    "discount_account": null,
			    "amount_after_discount": 10,
			    "google_map": null,
			    "warehouse_destination_name": "My Company",
			    "delivery_status": "pending_delivery",
			    "warehouse_name": null,
			    "postage_total": null,
			    "amount_total": 10,
			    "collaborators": null,
			    "name": "WH/IN/00002",
			    "total_way": null,
			    "stock_outin_date": "2017-04-11 02:49:12",
			    "forecast_time": null,
			    "customer_type": null,
			    "location_dest_id": 15,
			    "end_time": null,
			    "end_point": {
			        "lat": null,
			        "lng": null,
			        "id": null,
			        "name": null
			    },
			    "discount_value": null,
			    "start_point": {
			        "lat": null,
			        "lng": null,
			        "id": null,
			        "name": null
			    }
			}
		]
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

## Delivery [/api/wholesale/stock.picking/validate/{id}]
Validate delivery

### Validate delivery[PUT]
Validate stock picking
    
+ Parameters
    + id: 1 (required) - Unique identifier for a delivery

+ Response 200 (application/json)
    + Body
        ```js
        {
            "success": True,
            "msg": "Success"
        }
        ```

    + Schema
        ```js
        {
            "success": {
                "type": "boolean",
                "mean": "Kết quả trả về"
            },
            "msg": {
                "type": "string",
                "mean": ""
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
