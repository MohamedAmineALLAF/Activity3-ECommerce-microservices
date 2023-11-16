# Microservices-Based Billing System

This project implements a microservices architecture to manage invoices containing products associated with a customer.

## Microservices Overview:

1. **customer-service:**
    - Manages customer-related operations.
    - Entities: [Customer.java](screenshots/Customer-entity.PNG), [CustomerProjection.java](screenshots/CustomerProjection-entity.PNG)
    - Repositories: [CustomerRepository.java](screenshots/Customer-rest-repo.jpg)
    - Configuration: [application.properties](screenshots/customer-application-properties.png)
    - Data Initialization:


2. **inventory-service:**
    - Manages product-related operations.
    - Entities: [Product.java](screenshots/Product-entity.PNG), [ProductProjection.java](screenshots/ProductProjection-entity.PNG)
    - Repositories: [ProductRepository.java](screenshots/Product-rest-repo.jpg)
    - Configuration: [application.properties](screenshots/product-application-properties.png)
    - Data Initialization:


3. **gateway-service:**
    - Implements Spring Cloud Gateway for dynamic routing.
    - Configuration: [application.yml](screenshots/dynamic-routes-1.jpg), [Dynamic Routes Bean](screenshots/dynamic-routes-2.jpg)

4. **discovery-service:**
    - Enables Eureka for service discovery.
    - Configuration: [application.properties](screenshots/eureka-properties.jpg)

5. **billing-service:**
    - Manages billing operations and communicates with other microservices.
    - Entities: [Bill.java](screenshots/Bill-entity.PNG), [ProductItem.java](screenshots/ProductItem-entity.PNG)
    - Models: [Customer.java](screenshots/Customer-model.PNG), [Product.java](screenshots/Product-model.PNG)
    - Repositories: [BillRepository.java](screenshots/Bill-rest-repo.jpg), [ProductItemRepository.java](screenshots/ProductItem-rest-repo.jpg)
    - Services: [BillingService.java](screenshots/BillingService-service.jpg)
    - Web: [BillRestController.java](screenshots/BillRestController-controller.jpg)
    - Communication with Other Microservices:
        - [CustomerRestClient.java](screenshots/CustomerRestClient-feign.jpg)
        - [ProductRestClient.java](screenshots/ProductRestClient-feign.jpg)



## How to Run:

1. **Build and Run Each Microservice:**
    - For each microservice (customer-service, inventory-service, gateway-service, discovery-service, billing-service), navigate to its root directory and run `./mvnw spring-boot:run`.

2. **Accessing Services:**
    - After starting the services, you can access the Eureka Dashboard at [http://localhost:8761](http://localhost:8761).

3. **Billing Service Endpoint:**
    - The billing service provides an endpoint to retrieve a full bill including customer and product details. Example: [http://localhost:8084/fullBill/1](http://localhost:8084/fullBill/1)
