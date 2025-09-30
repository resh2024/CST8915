# CST8915 Lab 3

### Link to YouTube Demo video

https://www.youtube.com/watch?v=F_5vhjH2PL0

---

### Q1) What challenges did you encounter when configuring environment variables in the GitHub Actions workflow?

Ans) One challenge was making sure that environment variables defined in GitHub Secrets were correctly referenced inside the workflow. I initially mispelled the url so I was unable to load up the store-front to load up the products and process orders.

---

### Q2) How does deploying microservices on Azure Web App Service differ from running them locally?

Ans) When I run services locally, I usually just start them with a simple command like python app.py or npm start, and I can use a .env file for settings. On Azure Web App Service, it works a bit differently. Azure gives the app its own PORT to run on, and I have to set environment variables in the App Service settings instead of using .env. Deployment is done through pipelines or containers instead of just running the file. Also, Azure takes care of things like scaling, logging, and networking, so I need to make sure the app is set up to work in that environment.

---

### Q3) Why is it important to use environment variables for configurations in a cloud environment?

Ans) Environment variables are important because they keep configuration separate from the code. This way, I don’t have to hardcode sensitive info like API keys or database passwords. It also makes it easy to change settings for different environments (dev, test, prod) without touching the code. In the cloud, platforms like Azure handle environment variables securely, which helps with both security and flexibility.

---

### Repository Links

#### Order-Service Repo Link

https://github.com/resh2024/order-service-lab2

---

#### Product-Service Repo Link

https://github.com/resh2024/product-service-python

---

#### Store-Front Repo Link

https://github.com/resh2024/store-front-lab2

---
