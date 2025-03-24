## Client Testing

### POST Product in Postman

![POST Product](https://github.com/cassorr/springboot-lab4/blob/master/images/POSTproduct.png)

### GET Products from Postman

![GET Product](https://github.com/cassorr/springboot-lab4/blob/master/images/GETproduct.png)

## Post Tutorial Questions

1. **Why is it important to create separate databases for each microservice (e.g., `product_service`, `order_service`, `inventory_service`)?**

2. **What role does Flyway play in managing the database schema, and how does it ensure consistency across environments?**

3. **How does Spring Data JPA simplify working with databases in each of the microservices?**

4. **In the `InventoryService`, why did we use the `@Transactional(readOnly = true)` annotation, and what is its significance?**

5. **In a microservices architecture, what are some challenges when ensuring communication between the Product, Order, and Inventory Services?**

6. **What are the advantages of using TestContainers for integration testing with MySQL in this lab?**

