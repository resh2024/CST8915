# CST8915 Lab 7

## Link to YouTube Demo video

https://www.youtube.com/watch?v=XKUBDqKiIwE

## Whether RabbitMQ is a stateless or stateful application

RabbitMQ is a stateful application because it stores data such as messages, queues, and user settings. This data needs to persist even if the service restarts.

## The implications of running RabbitMQ without persistent storage

If RabbitMQ runs without persistent storage, all messages and queue data are lost when the container or pod restarts. This means any unprocessed messages disappear, which can disrupt communication between services and cause data loss.

## What happens when the RabbitMQ pod is deleted or restarted

When the RabbitMQ pod is deleted or restarted, Kubernetes creates a new pod with a clean state. Since there’s no persistent volume, RabbitMQ starts fresh — all previous messages, queues, and configurations are gone.

## Potential solutions to this problem (research-based)

RabbitMQ should be deployed as a StatefulSet with a PersistentVolumeClaim (PVC) to maintain data between restarts. This setup ensures data durability and consistent broker state. Alternatively, clustering RabbitMQ across multiple nodes or using managed message brokers can improve reliability. (Klishin, 2020)

## Does using Azure Service Bus solve the issues identified with RabbitMQ configuration in this Lab?

Yes. Azure Service Bus is a fully managed, cloud-based message broker. It automatically handles persistence, fault tolerance, and scaling, so you don’t have to manage storage or worry about data loss if a node fails. This removes the configuration and persistence issues seen with RabbitMQ in Kubernetes.

## Reference (APA 7th edition)

Klishin, M. (2020, August 10). Deploying rabbitmq to kubernetes: What’s involved?: Rabbitmq. RabbitMQ RSS. https://www.rabbitmq.com/blog/2020/08/10/deploying-rabbitmq-to-kubernetes-whats-involved
