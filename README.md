# How to run the application
1. Install XAMPP ( download it from [Link here](https://www.apachefriends.org) )
2. Open xampp control panel and start `Apache` and `mySQL` modules. Also pay attention to the 'port' that the `mySQL` runs on.
3. Change the following properties in `application.properties` file such that it is suitable for your database configuration

   ```
   spring.datasource.url=jdbc:mysql://localhost:3306/supermarketdb?createDatabaseIfNotExist=true
   spring.datasource.username=root
   spring.datasource.password=
   ```
4. Install Maven ( if you dont know, how to install mevan; then watch this [Link Here](https://youtu.be/WASIyomqarc))
5. Run following command `mvn spring-boot:run` in the terminal inside project root directory.
6. Install Postman and send following requsts to test ( if you never useed postman watch this [Link Here](https://youtu.be/CLG0ha_a0q8) )
   ```
   POST => http://localhost:8080/api/v1/item/create
   ```
   ```
    {
        "name": "book cr 160 pages",
        "price": 200.00,
        "quantity": 30
    }
   ```
   ```
   POST => http://localhost:8080/api/v1/item/create
   ```
   ```
    {
        "name": "book cr 120 pages",
        "price": 150.00,
        "quantity": 40
    }
   ```
   ```
   GET => http://localhost:8080/api/v1/item/read/{id}
   ```
   ```
   PUT => http://localhost:8080/api/v1/item/update/{id}
   ```
   ``` 
    {
        "name": "Tennis Ball",
        "price": 300.00,
        "quantity": 25
    }
   ```
   ```
   DELETE => http://localhost:8080/api/v1/item/delete/{id}
   ```
   ```
   Note : item deletion unsuccessful ! 
   Items cannot be deleted since if you delete an item,
   a mismatch between order and order details may occur.
   When a item is deleted related rows in order detail also deleted,
   then total_price pertaining to a order calculated from order_detail
   table are not going to equal with the total in order table.
   ```

   ```
   POST => http://localhost:8080/api/v1/customer/create
   ```
   ```
    {
        "name": "Lahiru",
        "email": "lahirun@gmail.com"
    }
   ```
   ``` 
   GET => http://localhost:8080/api/v1/customer/read/{id}
   ```
   ``` 
   PUT => http://localhost:8080/api/v1/customer/update/{id}
   ```
   ```
    {
        "name": "Eshan",
        "email": "eshan@gmail.com"
    }
   ```
   ```
   DELETE => http://localhost:8080/api/v1/customer/delete/{id}
   ```
   ```
   POST => http://localhost:8080/api/v1/order/create
   ```
   ```
    {
      "order": {
        "customer": {
          "customerId": 1
        },
        "orderDate": "2023-08-20"
      },
      "orderDetails": [
        {
          "item": {
            "itemId": 1
          },
          "quantity": 1
        },
        {
          "item": {
            "itemId": 2
          },
          "quantity": 3
        }
      ]
    }
   ```
