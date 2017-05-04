# Group Wholesale - Customer
    CURD Customer support wholesale

## Customer [/api/wholesale/res.partner]
Customer (getlist / create)

### Create customer [POST]
Create Create customer

+ Request JSON Message
    + Body
        ```js
        {
              "company_type": "person",
              "parent_id": 1,
              "name": "Nguyễn Ngọc Lương",
              "street": "458 Phan Văn Trị",
              "city_id": 68,
              "district_id": 835,
              "ward_id": 12778,
              "website": "www.xblue55.github.io",
              "agent_channel_id": 1,
              "tags": "1,2,3,4",
              "sale_persion": "CDF00242",
              "sale_persion_2": "CDF00242",
              "phone": "0988077558",
              "mobile": "0988077559",
              "email": "nnluong.it2@gmail.com",
              "title": 1,
              "source_id": 1,
              "customer_type": "cash",
              "tax_code": "123123123",
              "comment": "Thằng này tốt lắm",
              "function": "devoloper",
              "property_payment_term_id": 1,
              "delivery_service": "partner",
              "property_product_pricelist": 1,
              "child_ids": [
                {
                  "type": "contact",
                  "name": "Nguyễn Ngọc Út",
                  "function": "tester",
                  "email": "tester@gmail.com",
                  "phone": "0988888888",
                  "mobile": "097777777",
                  "comment": "Thằng này ko liên hệ được đâu",
                  "street": "468 Phan văn trị",
                  "city_id": 68,
                  "district_id": 835,
                  "ward_id": 12778
                },
                "create_opportunity": {
                		"name": "Khách hàng tìm năng đấy",
                		"planned_revenue": 1000000,
                		"rating": "2"
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
            "parent_id" : {
                "type": "int",
                "requried": false,
                "mean": "Id của partner với company_type = company"
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
            "agent_chanel_id": {
                "type": "integer",
                "mean": "Loại khách hàng MT/GT.... Mapping"
            },
            "tags": {
                "type": "string",
                "mean": "Phân loại khách hàng, truyền lên id,id1,id2,id3 .... Đồng bộ"
            },
            "sale_persion": {
                "type": "string",
                "mean": "Mã nhân viên 1"
            },
            "sale_persion_2": {
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
            "tax_code": {
                "type": "string",
                "mean": "Mã số thuế"
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
            },
            "contact_title_id": {
                "type": "integer",
                "mean": "Mr, misss..... bla. Đồng bộ"
            },
            "contact_name": {
                "type": "string",
                "mean": "Tên người liên hệ khi company_type company"
            },
            "child_ids":{
                [
                    {
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
            },
            "create_opportunity": {
            		"name": {
            			"type": "string",
            			"mean": "Tên của pipeline"
            		},
            		"planned_revenue": {
            			"type": "float",
            			"mean": "Doanh thu dự kiến"
            		},
            		"priority": {
            			"type": "enum('0','1','2','3')",
            			"mean": "điểm đánh giá, giá trị là string"
            		}
            }
        }
        ```

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
                "parent_id" : 1,
                "sale_person": null,
                "sale_person_2": null,
                "team_id": null,
                "street": "86/8 Phổ quang",
                "agent_chanel_id": null,
                "property_product_pricelist": 1,
                "id": 12,
                "property_payment_term_id": null,
                "title": null,
                "tax_code": "12345676543",
                "customer_id": "000003",
                "delivery_service": null,
                "email": "farm@gmail.com",
                "website": null,
                "contact_title_id": 1,
                "contact_name" : "Nguyễn Ngọc Lương",
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
                "tags": [
                  {
                    "id": 1,
                    "name": "Sale"
                  }
                ]
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
                "parent_id" : 1,
                "sale_person": null,
                "sale_person_2": null,
                "team_id": null,
                "street": "86/8 Phổ quang",
                "agent_chanel_id": null,
                "property_product_pricelist": 1,
                "id": 12,
                "property_payment_term_id": null,
                "title": null,
                "tax_code": "12345676543",
                "customer_id": "000003",
                "delivery_service": null,
                "email": "farm@gmail.com",
                "website": null,
                "contact_title_id": 1,
                "contact_name" : "Nguyễn Ngọc Lương",
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
                "tags": [
                  {
                    "id": 1,
                    "name": "Sale"
                  }
                ]
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
              "company_type": "person",
              "parent_id": 1,
              "name": "Nguyễn Ngọc Lương",
              "street": "458 Phan Văn Trị",
              "city_id": 68,
              "district_id": 835,
              "ward_id": 12778,
              "website": "www.xblue55.github.io",
              "agent_chanel_id": 1,
              "tags": "1,2,3,4",
              "sale_persion": "CDF00242",
              "sale_persion_2": "CDF00242",
              "phone": "0988077558",
              "mobile": "0988077559",
              "email": "nnluong.it2@gmail.com",
              "title": 1,
              "source_id": 1,
              "customer_type": "cash",
              "tax_code": "123123123",
              "comment": "Thằng này tốt lắm",
              "function": "devoloper",
              "property_payment_term_id": 1,
              "delivery_service": "partner",
              "property_product_pricelist": 1,
              "child_ids": [
                {
                  "type": "contact",
                  "name": "Nguyễn Ngọc Út",
                  "function": "tester",
                  "email": "tester@gmail.com",
                  "phone": "0988888888",
                  "mobile": "097777777",
                  "comment": "Thằng này ko liên hệ được đâu",
                  "street": "468 Phan văn trị",
                  "city_id": 68,
                  "district_id": 835,
                  "ward_id": 12778
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

### Edit customer [PUT]
Edit customer
    
+ Parameters
    + id: 12 (required) - Unique identifier for a customer

+ Request JSON Message
    + Body
        ```js
        {
            "company_type" : "person",
            "parent_id": 1,    
            "name": "Nguyễn Ngọc Lương",
            "street": "458 Phan Văn Trị",
            "city_id": 65,
            "district_id": 835,
            "ward_id": 12778,
            "website": "www.xblue55.github.io",
            "agent_chanel_id": 1,
            "tags": "1,2,3,4",
            "sale_persion": "CDF00242",
            "sale_persion_2": "CDF00242",
            "phone": "0988077558",
            "mobile": "0988077559",
            "email": "nnluong.it2@gmail.com",
            "title": 1,
            "source_id" : 1,
            "customer_type": "cash",
            "tax_code": "123513123",
            "comment": "Thằng này tốt lắm",
            "function": "devoloper",
            "property_payment_term_id": 1,
            "delivery_service": "partner",
            "property_product_pricelist": 1,
            "contact_title_id": 1,
            "contact_name" : "Lương",
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
            "parent_id" : {
                "type": "int",
                "requried": false,
                "mean": "Id của partner với company_type = company"
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
            "agent_chanel_id": {
                "type": "integer",
                "mean": "Loại khách hàng MT/GT.... Mapping"
            },
            "tags": {
                "type": "string",
                "mean": "Phân loại khách hàng, truyền lên id,id1,id2,id3 .... Đồng bộ"
            },
            "sale_persion": {
                "type": "string",
                "mean": "Mã nhân viên 1"
            },
            "sale_persion_2": {
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
            "tax_code": {
                "type": "string",
                "mean": "Mã số thuế"
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
            "contact_title_id": {
                "type": "integer",
                "mean": "Mr, misss..... bla. Đồng bộ"
            },
            "contact_name": {
                "type": "string",
                "mean": "Tên người liên hệ khi company_type company"
            },
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
        "count": 1,
        "results": [
            "comment": null,
            "function": null,
            "city_id": null,
            "company_type": "person",
            "parent_id" : 1,
            "sale_person": null,
            "sale_person_2": null,
            "team_id": null,
            "street": "86/8 Phổ quang",
            "agent_chanel_id": null,
            "property_product_pricelist": 1,
            "id": 12,
            "property_payment_term_id": null,
            "title": null,
            "tax_code": "12345676543",
            "customer_id": "000003",
            "delivery_service": null,
            "email": "farm@gmail.com",
            "website": null,
            "contact_title_id": 1,
            "contact_name" : "Nguyễn Ngọc Lương",
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
            "tags": [
              {
                "id": 1,
                "name": "Sale"
              }
            ]
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

