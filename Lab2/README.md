# CST8915 Lab 2

### Link to YouTube Demo video

https://www.youtube.com/watch?v=SXJM2i2bYO4

---

#### Q1) What changes did you make to the order-service and product-service to comply with the Configurations and Backing Services factors of the 12-Factor App methodology?

Ans) To follow the Configurations and Backing Services principles, I updated each service to use environment variables instead of hard-coded values. I created separate .env files for the order-service, product-service, and store-front, and used tools like dotenv and proper config loading to make sure each service reads its settings from the environment. This makes the services easier to manage and more flexible across different environments.

#### Q2) Why is it important to use environment variables instead of hard-coding configurations in your application?

Ans) Using environment variables keeps sensitive info like connection strings and ports out of the code, which is safer and cleaner. It also lets us change settings without touching the code, making it easier to move between development, testing, and production setups.

#### Q3) Why is it important to have separate repositories for each microservice? How does this help maintain independence and scalability of each service?

Ans) Each microservice was pushed to its own GitHub repository order-service, product-service, and store-front so they each have a separate codebase with version control. This setup helps keep the services independent, makes collaboration easier, and allows each one to be scaled or updated without affecting the others

---

### Repository Links

#### Order-Service Repo Link

https://github.com/resh2024/order-service-lab2

---

#### Product-Service Repo Link

https://github.com/resh2024/product-service-lab2

---

#### Store-Front Repo Link

https://github.com/resh2024/store-front-lab2

---
