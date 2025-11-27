# CST8915 Lab 8

## Link to YouTube Demo video

https://www.youtube.com/watch?v=z_QfcT_xeyE

## Task 2: Improving and Extending the Deployment

The original deployment ran MongoDB and RabbitMQ inside Kubernetes with **ephemeral storage**, meaning all data was lost if pods were deleted or the cluster restarted. To address this, I implemented persistence and high availability for both services.

---

### 1. MongoDB: High Availability and Persistence

- **PersistentVolumeClaim (PVC):**  
  Added a `volumeClaimTemplates` section to the MongoDB StatefulSet so each replica has its own persistent volume. This ensures data is stored on durable disks and survives pod restarts.

- **Replica Set:**  
  Increased replicas to `3` and configured the StatefulSet with a headless service (`clusterIP: None`). This provides stable DNS names (`mongodb-0.mongodb`, `mongodb-1.mongodb`, etc.) and allows MongoDB to form a replica set. Replica sets improve availability by automatically electing a new primary if one node fails.

- **Result:**  
  MongoDB now has fault tolerance, data durability, and can continue serving requests even if one pod goes down.

---

### 2. RabbitMQ: Persistent Message Storage

- **PersistentVolumeClaim (PVC):**  
  Mounted a persistent volume at `/var/lib/rabbitmq` using `volumeClaimTemplates`. This ensures queues and messages are stored durably.

- **ConfigMap:**  
  Kept the existing ConfigMap mount for plugins and definitions so RabbitMQ’s configuration remains intact.

- **Result:**  
  RabbitMQ now retains queues and messages across pod restarts, eliminating data loss during failures.

---

### 3. Azure Managed Service Alternatives

Instead of self‑hosting, Azure offers managed services that provide built‑in persistence, scaling, and availability:

- **Azure Cosmos DB (MongoDB API):**  
  A fully managed NoSQL database that supports MongoDB drivers. It provides replication, global distribution, automatic backups, and elastic scaling, removing the need to manage StatefulSets and PVCs manually.

- **Azure Service Bus:**  
  A managed enterprise messaging service with queues and topics. It ensures durable message storage, high availability, and seamless integration with Azure applications. It scales automatically and handles failover without manual intervention.

- **Azure Event Hubs (alternative to RabbitMQ for streaming):**  
  A managed event ingestion service designed for high‑throughput scenarios like telemetry or IoT. It provides persistence and integrates with analytics services.

---
