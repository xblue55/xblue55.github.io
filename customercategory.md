# Group Wholesale - Customer category
  CURD cb.type.customer.category support wholesale


## Customer category [/api/wholesale/customer.category]
Customer category (getlist)

### Get customer category [GET]
Get customer category

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
      "count": 2,
      "results": [
        {
          "display_name": "All",
          "name": "All",
          "parent_id": null,
          "type_code": "ALL",
          "type_des": "",
          "id": 1
        },
        {
          "display_name": "All / Saleable",
          "name": "Saleable",
          "parent_id": 1,
          "type_code": "SALE",
          "type_des": "",
          "id": 2
        }
      ]
    }
    ```
  + Schema
    ```js
    {
      "display_name": {
        "type": "string",
        "mean": "Tên hiển thị category"
      },
      "name": {
        "type": "string",
        "mean": "Tên category"
      },
      "parent_id": {
        "type": "interger",
        "mean": "ID category cha"
      },
      "type_code": {
        "type": "string",
        "mean": "Tên rút gọn category"
      Ư,
      "type_des": {
        "type": "string",
        "mean": "Mô tả category"
      },
      "id": {
        "type": "interger",
        "mean": "ID category"
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

## Customer category [/api/wholesale/customer.category/{id}]
Customer category (getdetail)

### Get customer category detail [GET]
Get customer category detail

+ Parameters
  + id: 2 (required) - Unique identifier for a customer category

+ Response 200 (application/json)
  + Body
    ```js
    {
      "display_name": "All / Saleable",
      "name": "Saleable",
      "parent_id": 1,
      "type_code": "SALE",
      "type_des": "",
      "id": 2
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
