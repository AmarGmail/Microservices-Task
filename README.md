# Microservices-Task

## Overview
This document provides details on testing various services after running the `docker-compose` file. These services include User, Product, Order, and Gateway Services. Each service has its own endpoints for testing purposes.

---

## Services and Endpoints

### **User Service**
- **Base URL:** `http://localhost:3000`
- **Endpoints:**
  - **List Users:**  
    ```
    curl http://localhost:3000/users
    ```
    Or open in your browser: [http://localhost:3000/users](http://localhost:3000/users)

---

### **Product Service**
- **Base URL:** `http://localhost:3001`
- **Endpoints:**
  - **List Products:**  
    ```
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)


---

### **Order Service**
- **Base URL:** `http://localhost:3002`
- **Endpoints:**
  - **List Orders:**  
    ```
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)

---

### **Gateway Service**
- **Base URL:** `http://localhost:3003/api`
- **Endpoints:**
  - **Users:**  
    ```
    curl http://localhost:3003/api/users
    ```
  - **Products:**  
    ```
    curl http://localhost:3003/api/products
    ```
  - **Orders:**  
    ```
    curl http://localhost:3003/api/orders
    ```
  - **outputs:**
  ```
  hi@USER:~/projects/herovired/skill_test_v1/Microservices-Task/Microservices$ curl http://localhost:3003/api
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Error</title>
</head>
<body>
<pre>Cannot GET /api</pre>
</body>
</html>
hi@USER:~/projects/herovired/skill_test_v1/Microservices-Task/Microservices$ curl http://localhost:3003/api/users
[{"id":1,"name":"John Doe"},{"id":2,"name":"Jane Smith"}]hi@USER:~/projects/herovired/skill_test_v1/Microservices-Task/Microservices$ curl http://localhost:3003/api/products
[{"id":1,"name":"Laptop","price":999},{"id":2,"name":"Phone","price":699}]hi@USER:~/projects/herovired/skill_test_v1/Microservices-Task/Microservices$ curl http://localhost:3003/api/orders
[]hi@USER:~/projects/herovired/skill_test_v1/Microservices-Task/Microservices$
  ```  
---

## Instructions
1. Start all services using the `docker-compose` file:
   ```
   hi@USER:~/projects/herovired/skill_test_v1/Microservices-Task/Microservices$ docker-compose up
   
   hi@USER:~/projects/herovired/skill_test_v1/Microservices-Task/Microservices$ docker ps
CONTAINER ID   IMAGE                 COMMAND                  CREATED         STATUS         PORTS                                         NAMES
ab8801d7b23a   order-service:1.0     "docker-entrypoint.s…"   4 seconds ago   Up 4 seconds   0.0.0.0:3002->3002/tcp, [::]:3002->3002/tcp   order-service
2ac6248cbed7   gateway-service:1.1   "docker-entrypoint.s…"   4 seconds ago   Up 4 seconds   0.0.0.0:3003->3003/tcp, [::]:3003->3003/tcp   gateway-service
8d13e9566f72   user-service:1.1      "docker-entrypoint.s…"   4 seconds ago   Up 4 seconds   0.0.0.0:3000->3000/tcp, [::]:3000->3000/tcp   user-service
19a64eda109a   product-service:1.0   "docker-entrypoint.s…"   4 seconds ago   Up 4 seconds   0.0.0.0:3001->3001/tcp, [::]:3001->3001/tcp   product-service
   ```
2. Once the services are running, use the above endpoints to verify the functionality.

Happy testing!
