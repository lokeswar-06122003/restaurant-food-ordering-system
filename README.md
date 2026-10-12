# Restaurant Food Ordering System

A microservices-based restaurant food ordering application developed as an MCA academic project using Python, Flask, SQLite, REST APIs, and a browser-based interactive user interface.

## 1. Project Overview

The Restaurant Food Ordering System allows customers to browse restaurants, explore menus, manage a cart, apply coupons, place orders, make simulated payments, and track deliveries.

The project demonstrates microservices architecture, API Gateway routing, Service Discovery, database isolation, API versioning, Circuit Breaker, Saga Pattern, compensating actions, fault tolerance, and REST API testing.

## 2. Technology Stack

- Programming language: Python
- Backend framework: Flask
- Database: SQLite
- Inter-service communication: REST APIs
- HTTP client: Requests
- Frontend: HTML, CSS, JavaScript
- Automated testing: pytest
- API testing: Postman
- Development environment: Visual Studio Code
- Version control: Git and GitHub

## 3. Architecture

The client interacts with the backend through the API Gateway.

The API Gateway routes requests to six independent business microservices. Each business microservice owns its own SQLite database.

### Business Microservices

1. User Service
2. Restaurant/Menu Service
3. Order Service
4. Payment Service
5. Delivery Service
6. Notification Service

### Infrastructure Components

- API Gateway
- Service Registry / Service Discovery

The Order Service coordinates the distributed ordering workflow using the Saga Pattern and compensating actions.

## 4. Business Functionalities

1. User and Customer Management
2. Restaurant and Menu Management
3. Order Management
4. Payment Management
5. Delivery Management
6. Notification Management
7. Cart Management
8. Search and Filter
9. Review and Rating Management
10. Offers and Coupon Management

## 5. Database Design

Each business microservice owns a separate database.

| Service | Database |
| --- | --- |
| User Service | user_db |
| Restaurant/Menu Service | restaurant_db |
| Order Service | order_db |
| Payment Service | payment_db |
| Delivery Service | delivery_db |
| Notification Service | notification_db |

Services must not directly access another service's database. Cross-service communication must use REST APIs.

## 6. Project Structure

- `frontend/` — browser-based user interface
- `api-gateway/` — client entry point and API routing
- `service-registry/` — service registration and discovery
- `user-service/` — customer management
- `restaurant-service/` — restaurants, menus, reviews and ratings
- `order-service/` — orders, cart, coupons, Saga and Circuit Breaker
- `payment-service/` — simulated payments and refunds
- `delivery-service/` — delivery assignment and status
- `notification-service/` — order notifications
- `tests/` — automated tests
- `docs/` — project documentation

## 7. Setup Instructions

### Prerequisites

Install Python 3.11 or 3.12, Git, and Visual Studio Code.

### Create a virtual environment

From the project root, run:

```powershell
python -m venv .venv
```

### Activate the virtual environment

On Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

### Install dependencies

```powershell
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### Running the application

The services and frontend will be configured and implemented in stages. Refer to this README and the individual service instructions for the final startup commands once implementation is complete.

## 8. API Versioning

The project will provide versioned endpoints such as:

- `/api/v1/orders` — basic order API contract
- `/api/v2/orders` — enhanced order response with additional order details

The differences between API versions will be documented and tested.

## 9. Resilience and Distributed Transactions

### Circuit Breaker

The Order Service will use a Circuit Breaker when communicating with the Payment Service. The implementation will demonstrate CLOSED, OPEN and HALF-OPEN states.

### Saga Pattern

The Order Service will coordinate order creation, payment processing, delivery assignment and notifications through REST APIs.

When a step fails, the Saga will execute suitable compensating actions to restore a consistent business state.

## 10. Testing

The project will include:

- REST API CRUD tests
- Input validation and error-handling tests
- API Gateway routing tests
- Service Discovery tests
- Database isolation checks
- API versioning tests
- Circuit Breaker failure and recovery tests
- Saga success and compensation tests
- End-to-end ordering tests

Only tests that have actually been executed will be reported as completed.

## 11. Security and Academic Use

Payments are simulated for demonstration purposes. Do not use real payment credentials or sensitive personal information.

Authentication, validation and error handling will be implemented as part of the relevant development phases.

## 12. Development Status

Project setup and implementation are being completed incrementally. Individual services and architecture features will be marked complete only after implementation and testing.

## 13. Future Enhancements

- Integration with a legitimate payment provider in a test environment
- Real-time delivery updates
- Enhanced authentication and authorization
- Deployment to a cloud platform
- Additional automated integration tests

## 14. Academic Project

**Project Title:** Restaurant Food Ordering System  
**Architecture:** Microservices  
**Purpose:** MCA academic mini project
