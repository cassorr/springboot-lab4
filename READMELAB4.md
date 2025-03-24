## Postman Testing

### POST Product in Postman

![POST Product](https://github.com/cassorr/springboot-lab4/blob/master/images/POSTproduct.png)

### GET Products from Postman

![GET Product](https://github.com/cassorr/springboot-lab4/blob/master/images/GETproduct.png)

## Post Tutorial Questions

1. **Why is it important to create separate databases for each microservice (e.g., `product_service`, `order_service`, `inventory_service`)?**

  Becuase we should have loose coupling and high cohension. This way, services can be independently deployable because the services can be deployed or rolled back without worrying about shared database schema conflicts.

2. **What role does Flyway play in managing the database schema, and how does it ensure consistency across environments?**

  Flyway keeps track of DB changes by running versioned SQL scripts in order and recording which ones have already been run. With scripts `V1__init.sql`, `V2__add_column.sql`, Flyway will make sure they run in the right order and only once, no matter where you deploy.
  
3. **How does Spring Data JPA simplify working with databases in each of the microservices?**

  Spring Data JPA takes care of a lot of boilerplate code like writing SQL queries or managing connections. You just define interfaces, and it auto-generates common methods like save, findById, and delete—making it way easier to work with databases. I use JPA for my capstone project and it makes it to where I don't have to spend time writing SQL and can just use JPA to manage methods pertaining to the DB.

4. **In the `InventoryService`, why did we use the `@Transactional(readOnly = true)` annotation, and what is its significance?**

  We use `@Transactional(readOnly = true)` to let spring boot know the method only reads from the DB and doesn’t make any changes. This helps with performance because it skips some unnecessary checks and makes the operation more efficient.

6. **In a microservices architecture, what are some challenges when ensuring communication between the Product, Order, and Inventory Services?**

  Some challenges include making sure services are always available when needed, handling network delays or failures, and keeping data consistent across all services. In systems like this that are event driven, there are challenges with event occurences might arrive out of order or even more than once, so there needs to be ways to handle that.

8. **What are the advantages of using TestContainers for integration testing with MySQL in this lab?**

  TestContainers lets me create a MySQL DB in Docker during tests, so I can test against an actual environment instead of a mock. This means I catch bugs early and avoid "works on my machine" problems — plus, it keeps the test database clean every time so I don't have to repeatedly delete stuff in the DB. 
