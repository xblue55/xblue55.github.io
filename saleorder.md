# Group Wholesale - Saleorder
    CURD saleorder support wholesale

## Order [/api/wholesale/sale.order]
Order (getlist / create)

### Create order [POST]
Create seo order

+ Request JSON Message
    + Body
        ```js
        {
            "customer_id": 4095,
            "partner_reciver_id": 4095,
            "partner_invoice_id": 4095,
            "partner_shipping_id": 4095,
            "sale_person":{
                "code":"CDF000247",
                "name":"CDF000247"
            },
            "warehouse_code":"KTT",
            "order_line":[
                {
                    "price_unit":20000.0,
                    "price_discount":0.0,
                    "product_id":237,
                    "product_uom_qty":1.0
                },
                {
                    "price_unit":24000.0,
                    "price_discount":1000.0,
                    "product_id":241,
                    "product_uom_qty":1.0,
                    "discount_type": "fixprice"
                }
            ],
            "category_id" : 1,
            "discount":10000.0,
            "source":"oss_wholesale",
            "order_channel":"wholesale",
            "template_id": 1,
            "pricelist_id": 1,
            "order_date": "3-10-2017 12:00:00",
            "validity_date" : "3-10-2017 12:00:00",
            "stock_tranfer_date" : "3-10-2017 12:00:00",
            "create_delivery": true,
            "register_payment": true
        }
        ```
    + Schema
        ```js
        {
            "type": "object",
            "properties": {
                "customer_id": {
                    "type" : "integer",
                    "required": "true",
                    "mean": "Khách hàng"
                },
                "partner_reciver_id": {
                    "type" : "integer",
                    "mean": "Người liên hệ (không chọn mặc định là khách hàng)"
                },
                "partner_invoice_id": {
                    "type" : "integer",
                    "required": "true",
                    "mean": "Người liên hệ (không chọn mặc định là khách hàng)"
                },
                "partner_shipping_id": {
                    "type" : "integer",
                    "required": "true",
                    "mean": "Người liên hệ (không chọn mặc định là khách hàng)"
                },
                "sale_person":{
                    "code": {
                        "type" : "string",
                        "required": "true",
                        "mean": "Mã user bán hàng. CDF0000"
                    },
                    "name": {
                        "type" : "string",
                        "required": "true",
                        "mean": "Tên user bán hàng"
                    }
                },
                "warehouse_code": {
                    "type" : "string",
                    "required": "true",
                    "mean": "Mã warehouse đã mapping"
                },
                "order_line":[
                    {
                        "price_unit":{
                            "type" : "double",
                            "required": "true",
                            "mean": "Giá. không nhập thì giá sẽ là giá sp"
                        },
                        "price_discount":{
                            "type" : "double",
                            "mean": "Khuyêến mãi trên line"
                        },
                        "product_id":{
                            "type" : "integer",
                            "mean": "Id sản phẩm"
                        },
                        "product_uom_qty": {
                            "type": "integer",
                            "mean": "Số lượng"
                        }
                    }
                ],
                "category_id" : {
                    "type": "integer",
                    "mean": "Id danh mục"
                },
                "discount":{
                    "type" : "double",
                    "mean": "Khuyến mãi"
                },
                "source":  {
                    "type": "enum('oss_wholesale')",
                    "mean": "Nguồn từ oss"
                },
                "order_channel": {
                    "type": "enum('wholesale')",
                    "mean": "Kênh wholesale"
                },
                "template_id": {
                    "type": "integer",
                    "mean": "Id template"
                },
                "pricelist_id": {
                    "type": "integer",
                    "mean": "Pricelist id áp dụng"
                },
                "order_date": {
                    "type": "string (%Y-%m-%d %H:%M:%S)",
                    "mean": "Ngày mua hàng"
                },
                "validity_date": {
                    "type": "string (%Y-%m-%d %H:%M:%S)",
                    "mean": "Ngày hết hạn"
                },
                "stock_tranfer_date":{
                    "type": "string (%Y-%m-%d %H:%M:%S)",
                    "mean": "Ngày giao hàng"
                },
                "create_delivery":{
                    "type": "boolean",
                    "mean": "Dành cho đơn hàng muốn xuất kho và tạo invoice. bán hàng sỉ tại cửa hàng",
                },
                "register_payment":{
                    "type": "boolean",
                    "mean": "thanh toán tại thời điểm bán hàng luôn,",
                }
            },
            "additionalProperties": false
        }
        ```

+ Response 200 (application/json)
    + Body
        ```js
        {
            "id": 1   
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

### Get order [GET]
Get sale order

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
                {
                    "user_id": {
                        "id": 22,
                        "name": "Hồ Minh Phú"
                    },
                    "name": "SO28048",
                    "order_line": [
                    {
                       "name": "Cà phê Máy - 100% Robusta - Gói 1kg",
                       "price_unit": 45000,
                       "product_uom_qty": 1,
                       "price_subtotal": 40909.090000000004,
                       "product_id": {
                            "categ_id": 9,
                            "barcode": "8110012300001",
                            "type": "product",
                            "id": 78,
                            "name": "Cà phê Máy - 100% Robusta - Gói 1kg"
                       },
                       "id": 60659,
                       "tax_id": [
                            {
                              "id": 4,
                              "name": "Thuế GTGT phải nộp 10%"
                            }
                        ]
                    }
                    ],
                    "state": "sale",
                    "date_order": "2017-04-04 15:58:42",
                    "partner_id": {
                        "customer_id": "003671",
                        "id": 4419,
                        "name": "06_Anh Phúc - Đà Nẵng"
                    },
                    "id": 28053,
                    "amount_total": 45000
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

## Order [/api/wholesale/sale.order/{id}]
Order (getdetail/update/detail)
### Get order detail [GET]
Get sale order detail
    
+ Parameters
    + id: 12 (required) - Unique identifier for a sale orrder

+ Response 200 (application/json)
    + Body
        ```js
        {
            "count": 1,
            "results": [
                {
                    "user_id": {
                        "id": 22,
                        "name": "Hồ Minh Phú"
                    },
                    "name": "SO28048",
                    "order_line": [
                    {
                       "name": "Cà phê Máy - 100% Robusta - Gói 1kg",
                       "price_unit": 45000,
                       "product_uom_qty": 1,
                       "price_subtotal": 40909.090000000004,
                       "product_id": {
                            "categ_id": 9,
                            "barcode": "8110012300001",
                            "type": "product",
                            "id": 78,
                            "name": "Cà phê Máy - 100% Robusta - Gói 1kg"
                       },
                       "id": 60659,
                       "tax_id": [
                            {
                              "id": 4,
                              "name": "Thuế GTGT phải nộp 10%"
                            }
                        ]
                    }
                    ],
                    "state": "sale",
                    "date_order": "2017-04-04 15:58:42",
                    "partner_id": {
                        "customer_id": "003671",
                        "id": 4419,
                        "name": "06_Anh Phúc - Đà Nẵng"
                    },
                    "id": 28053,
                    "amount_total": 45000
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

### Update order [PUT]
Update order
    
+ Parameters
    + id: 12 (required) - Unique identifier for a sale orrder

+ Request
    + Body
        ```js
        {
            "customer_id": 4095,
            "partner_reciver_id": 4095,
            "partner_invoice_id": 4095,
            "partner_shipping_id": 4095,
            "sale_person":{
                "code":"CDF000247",
                "name":"CDF000247"
            },
            "warehouse_code":"KTT",
            "order_line":[
                {
                    "id": 100,
                    "price_unit":20000.0,
                    "price_discount":0.0,
                    "product_id":237,
                    "product_uom_qty":1.0
                },
                {
                    "id": 200,
                    "price_unit":24000.0,
                    "price_discount":1000.0,
                    "product_id":241,
                    "product_uom_qty":1.0,
                    "discount_type": "fixprice",
                    "delete": 1
                },
                {
                    "price_unit":24000.0,
                    "price_discount":1000.0,
                    "product_id":243,
                    "product_uom_qty":1.0,
                    "discount_type": "fixprice"
                }
            ],
            "category_id" : 1,
            "discount":10000.0,
            "source":"oss_wholesale",
            "order_channel":"wholesale",
            "template_id": 1,
            "pricelist_id": 1,
            "order_date": "3-10-2017 12:00:00",
            "validity_date" : "3-10-2017 12:00:00",
            "stock_tranfer_date" : "3-10-2017 12:00:00"
        }
        ```
    + Schema
        ```js
        {
            "type": "object",
            "properties": {
                "customer_id": {
                    "type" : "integer",
                    "required": "true",
                    "mean": "Khách hàng"
                },
                "partner_reciver_id": {
                    "type" : "integer",
                    "mean": "Người liên hệ (không chọn mặc định là khách hàng)"
                },
                "partner_invoice_id": {
                    "type" : "integer",
                    "required": "true",
                    "mean": "Người liên hệ (không chọn mặc định là khách hàng)"
                },
                "partner_shipping_id": {
                    "type" : "integer",
                    "required": "true",
                    "mean": "Người liên hệ (không chọn mặc định là khách hàng)"
                },
                "sale_person":{
                    "code": {
                        "type" : "string",
                        "required": "true",
                        "mean": "Mã user bán hàng. CDF0000"
                    },
                    "name": {
                        "type" : "string",
                        "required": "true",
                        "mean": "Tên user bán hàng"
                    }
                },
                "warehouse_code": {
                    "type" : "string",
                    "required": "true",
                    "mean": "Mã warehouse đã mapping"
                },
                "order_line":[
                    {
                        "price_unit":{
                            "type" : "double",
                            "required": "true",
                            "mean": "Giá. không nhập thì giá sẽ là giá sp"
                        },
                        "price_discount":{
                            "type" : "double",
                            "mean": "Khuyêến mãi trên line"
                        },
                        "product_id":{
                            "type" : "integer",
                            "mean": "Id sản phẩm"
                        },
                        "product_uom_qty": {
                            "type": "integer",
                            "mean": "Số lượng"
                        },
                        "id" {
                            "type": "integer",
                            "mean": "Id line muốn edit"
                        },
                        "delete" {
                            "type": "integer",
                            "mean": "Nếu muốn xóa line đó thì thêm key delete và id, nếu ko có key delete va id thì mặc định là thêm mới, nếu thì có id thì là update line đó"
                        },
                    }
                ],
                "category_id" : {
                    "type": "integer",
                    "mean": "Id danh mục"
                },
                "discount":{
                    "type" : "double",
                    "mean": "Khuyến mãi"
                },
                "source":  {
                    "type": "enum('oss_wholesale')",
                    "mean": "Nguồn từ oss"
                },
                "order_channel": {
                    "type": "enum('wholesale')",
                    "mean": "Kênh wholesale"
                },
                "template_id": {
                    "type": "integer",
                    "mean": "Id template"
                },
                "pricelist_id": {
                    "type": "integer",
                    "mean": "Pricelist id áp dụng"
                },
                "order_date": {
                    "type": "string (%Y-%m-%d %H:%M:%S)",
                    "mean": "Ngày mua hàng"
                },
                "validity_date": {
                    "type": "string (%Y-%m-%d %H:%M:%S)",
                    "mean": "Ngày hết hạn"
                },
                "stock_tranfer_date":{
                    "type": "string (%Y-%m-%d %H:%M:%S)",
                    "mean": "Ngày giao hàng"
                }
            },
            "additionalProperties": false
        }
        ```
+ Response 200 (application/json)
    + Body
        ```js
        {
            "id": 1
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

### Delete order [DELETE]
Xóa 1 order
    
+ Parameters
    + id: 12 (required) - Unique identifier for a sale orrder

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