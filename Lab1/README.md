# Lab 1 CST8915

## Youtube video link for demo:

https://www.youtube.com/watch?v=Yjv5UEQ2ESo

## Brief techincal explanation:

### Order Service (Node.js):

The order-service is responsible for handling customer orders received from the store-front. When a customer places an order at from store-front the order-service processes the order details. It is built using Node.js as it's framework.

It sends order messages to the Order Queue (RabbitMQ) so they can be processed in the background instead of right away. It also communicates with the store-front through APIs to confirm orders.

---

### Product Service (Rust):

The product-service handles the product information, such as product details, availability, and pricing. It is built using Rust

This service interacts with the store-front, providing accurate and up-to date product details that customers see when browsing. It doesn’t directly talk to the order queue, but it indirectly supports orders by making sure customers have accurate product data before placing them.

---

### Store Front(Vue.js):

The store-front is the front-end web application that customers directly interact with. It’s built with Vue.js, the store-front shows products from the product-service and lets customers place orders that are then passed to the order-service.

The store-front bridges customers with backend services, sending requests to the product-service for product info and the order-service for orders, while hiding RabbitMQ and keeping the experience simple.

---
