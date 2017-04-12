# Group Wholesale - Delivery
    CURD Customer support wholesale

## Delivery [/api/wholesale/stock.picking]
Delivery (getlist)

### Get delivery [GET]
Get delivery

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
                    "name": "PXK/17/04/15/11/02/49/12/00002",
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
            "count": 1,
            "results": [
                {
                    "origin": {
                        "type": "string",
                        "mean": "Mả SO hoặc PO"
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
                    "name": "PXK/17/04/15/11/02/49/12/00002",
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

### Get customer [GET]
Get customer

+ Request
    ```js
    {
       "filters": "[('some_field_1', '=', some_value_1), ('some_field_2', '!=', some_value_2)]",   
       "offset": "interger",
       "limit": "interger",
       "order": "list_of_fields"
    }```
    

+ Response 200 (application/json)
    + Body
        ```js
        {
            "count": 1,
            "results": [
                "comment": null,
                "function": null,
                "city_id": null,
                "company_type": "person",
                "sale_person_2": null,
                "team_id": null,
                "street": "86/8 Phổ quang",
                "type_code": null,
                "property_product_pricelist": 1,
                "id": 12,
                "property_payment_term_id": null,
                "user_id": null,
                "title": null,
                "customer_id": "000003",
                "delivery_service": null,
                "email": "farm@gmail.com",
                "website": null,
                "child_ids": [
                    {
                      "function": null,
                      "comment": null,
                      "name": "Nguyễn Ngọc Lương",
                      "ward_id": null,
                      "mobile": null,
                      "district_id": null,
                      "id": 18,
                      "phone": null,
                      "street": "86/8 Phổ quang",
                      "city_id": null,
                      "type": "invoice",
                      "email": null
                    },
                    {
                      "function": null,
                      "comment": null,
                      "name": "Shipping",
                      "ward_id": null,
                      "mobile": null,
                      "district_id": null,
                      "id": 19,
                      "phone": null,
                      "street": "468 Phan văn trị",
                      "city_id": null,
                      "type": "delivery",
                      "email": null
                    }
                ],
                "phone": null,
                "name": "Farm",
                "ward_id": null,
                "mobile": null,
                "district_id": null,
                "customer_type": null,
                "source_id": null,
                "category_id": null
            ]
        }
        ```
    + Schema
        ```js
        {
            "count": 1,
            "results": [
                "comment": null,
                "function": null,
                "city_id": null,
                "company_type": "person",
                "sale_person_2": null,
                "team_id": null,
                "street": "86/8 Phổ quang",
                "type_code": null,
                "property_product_pricelist": 1,
                "id": 12,
                "property_payment_term_id": null,
                "user_id": null,
                "title": null,
                "customer_id": "000003",
                "delivery_service": null,
                "email": "farm@gmail.com",
                "website": null,
                "child_ids": [
                    {
                      "function": null,
                      "comment": null,
                      "name": "Nguyễn Ngọc Lương",
                      "ward_id": null,
                      "mobile": null,
                      "district_id": null,
                      "id": 18,
                      "phone": null,
                      "street": "86/8 Phổ quang",
                      "city_id": null,
                      "type": "invoice",
                      "email": null
                    },
                    {
                      "function": null,
                      "comment": null,
                      "name": "Shipping",
                      "ward_id": null,
                      "mobile": null,
                      "district_id": null,
                      "id": 19,
                      "phone": null,
                      "street": "468 Phan văn trị",
                      "city_id": null,
                      "type": "delivery",
                      "email": null
                    }
                ],
                "phone": null,
                "name": "Farm",
                "ward_id": null,
                "mobile": null,
                "district_id": null,
                "customer_type": null,
                "source_id": null,
                "category_id": null
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

## Customer [/api/wholesale/res.partner/{id}]
Customer (detail/update/delete)
### Get customer detail [GET]
Get sale customer detail
    
+ Parameters
    + id: 12 (required) - Unique identifier for a customer

+ Response 200 (application/json)
    + Body
        ```js
        {
            "comment": null,
            "function": null,
            "city_id": null,
            "company_type": "person",
            "sale_person_2": null,
            "team_id": null,
            "street": "86/8 Phổ quang",
            "type_code": null,
            "property_product_pricelist": 1,
            "id": 12,
            "property_payment_term_id": null,
            "user_id": null,
            "title": null,
            "customer_id": "000003",
            "delivery_service": null,
            "email": "farm@gmail.com",
            "website": null,
            "child_ids": [
                {
                  "function": null,
                  "comment": null,
                  "name": "Nguyễn Ngọc Lương",
                  "ward_id": null,
                  "mobile": null,
                  "district_id": null,
                  "id": 18,
                  "phone": null,
                  "street": "86/8 Phổ quang",
                  "city_id": null,
                  "type": "invoice",
                  "email": null
                },
                {
                  "function": null,
                  "comment": null,
                  "name": "Shipping",
                  "ward_id": null,
                  "mobile": null,
                  "district_id": null,
                  "id": 19,
                  "phone": null,
                  "street": "468 Phan văn trị",
                  "city_id": null,
                  "type": "delivery",
                  "email": null
                }
            ],
            "phone": null,
            "name": "Farm",
            "ward_id": null,
            "mobile": null,
            "district_id": null,
            "customer_type": null,
            "source_id": null,
            "category_id": null
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

### Edit customer [PUT]
Edit customer
    
+ Parameters
    + id: 12 (required) - Unique identifier for a customer

+ Request JSON Message
    + Body
        ```js
        {
            "company_type" : "person",          
            "name": "Nguyễn Ngọc Lương",
            "street": "458 Phan Văn Trị",
            "city_id": 65,
            "district_id": 835,
            "ward_id": 12778,
            "website": "www.xblue55.github.io",
            "type_code": 1,
            "category_id": "1,2,3,4",
            "user_code": "CDF00242",
            "user_code_2": "CDF00242",
            "phone": "0988077558",
            "mobile": "0988077559",
            "email": "nnluong.it2@gmail.com",
            "title": 1,
            "source_id" : 1,
            "customer_type": "cash",
            "comment": "Thằng này tốt lắm",
            "function": "devoloper",
            "property_payment_term_id": 1,
            "delivery_service": "partner",
            "property_product_pricelist": 1,
            "child_ids": [
                    {
                        "id": 45,
                        "type" : "contact",
                        "name" : "Nguyễn Ngọc Út",
                        "function": "tester",
                        "email": "tester@gmail.com",
                        "phone": "0988888888",
                        "mobile": "097777777",
                        "comment": "Thằng này ko liên hệ được đâu",
                        "street": "468 Phan văn trị",
                        "city_id": 65,
                        "district_id": 835,
                        "ward_id": 12778
                    }
                ]
            
        }
        ```
    + Schema
        ```js
        {
            "company_type" : {
                "type": "enum('person', 'company')",
                "requried": true,
                "mean": "Loại khách hàng công ty hay cá nhân"
            },          
            "name": {
                "type": "string",
                "requried": true,
                "mean": "Tên khách hàng"
            }, 
            "street": {
                "type": "string",
                "mean": "Địa chỉ"
            },
            "city_id": {
                "type": "integer",
                "mean": "Tỉnh/Thành phố"
            },
            "district_id": {
                "type": "integer",
                "mean": "Quận huyện"
            },
            "ward_id": {
                "type": "integer",
                "mean": "Phường xã"
            },
            "website": {
                "type": "string",
                "mean": "Website"
            },
            "type_code": {
                "type": "integer",
                "mean": "Loại khách hàng MT/GT.... Mapping"
            },
            "category_id": {
                "type": "string",
                "mean": "Phân loại khách hàng, truyền lên id,id1,id2,id3 .... Đồng bộ"
            },
            "user_code": {
                "type": "string",
                "mean": "Mã nhân viên 1"
            },
            "user_code_2": {
                "type": "string",
                "mean": "Mã nhân viên 2"
            },
            "phone": {
                "type": "string",
                "unique" : true
                "mean": "Số điện thoại"
            },
            "mobile": {
                "type": "string",
                "unique" : true
                "mean": "Số điện thoại di động"
            },
            "email": {
                "type": "string",
                "unique" : true
                "mean": "Email khách hàng"
            },
            "title": {
                "type": "integer",
                "mean": "Mr, misss..... bla. Đồng bộ"
            },
            "source_id" : {
                "type": "integer",
                "mean": "Nguồn khách hàng....Mapping"
            },
            "customer_type": {
                "type": "enum('cash', 'debts', 'deposit', 'internal')",
                "mean": "Loại thanh toán: Tiền mặt, công nợ, ký quỷ, nội bộ"
            },
            "comment": {
                "type": "string",
                "mean": "ghi chú khách hàng"
            },
            "function": {
                "type" : "string",
                "mean" : "Chức vụ"
            },
            "property_payment_term_id": {
                "type": "integer",
                "mean": "Kỳ hạn thanh toán ... Mapping"
            },
            "delivery_service": {
                "type": "enum(internal,partner,collaborators)",
                "mean": "Dịch vụ vẫn chuyển (nội bộ, Đối tác, Cộng tác viên)"
            },
            "property_product_pricelist": {
                "type": "integer",
                "mean": "Price list mặc định cho khách hàng... đồng bộ"
            }
            "child_ids": [
                    {
                        "id" : {
                            "type": "integer",
                            "mean" : "Nếu muốn update thông tin childs id thì truyền thêm id của childs_id đó vào đây"
                        }
                        "type" : {
                            "type": "enum(contact, invoice, delivery, other)"
                        },
                        "name": {
                            "type": "string",
                            "requried": true,
                            "mean": "Tên khách hàng"
                        },
                        "function": {
                            "type" : "string",
                            "mean" : "Chức vụ"
                        },
                        "phone": {
                            "type": "string",
                            "unique" : true
                            "mean": "Số điện thoại"
                        },
                        "mobile": {
                            "type": "string",
                            "unique" : true
                            "mean": "Số điện thoại di động"
                        },
                        "email": {
                            "type": "string",
                            "unique" : true
                            "mean": "Email khách hàng"
                        },
                        "comment": {
                            "type": "string",
                            "mean": "ghi chú khách hàng"
                        },
                        "street": {
                            "type": "string",
                            "mean": "Địa chỉ"
                        },
                        "city_id": {
                            "type": "integer",
                            "mean": "Tỉnh/Thành phố"
                        },
                        "district_id": {
                            "type": "integer",
                            "mean": "Quận huyện"
                        },
                        "ward_id": {
                            "type": "integer",
                            "mean": "Phường xã"
                        }
                    }
                ]
        }
        ```

+ Response 200 (application/json)

    ```js
    {
        "id": 12,
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

### Delete customer [DELETE]
Xóa 1 customer
+ Parameters
    + id: 12 (required) - Unique identifier for customer

+ Response 200 (application/json)
    + Body
        ```js
        {
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
