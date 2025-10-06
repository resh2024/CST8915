# CST8915 Lab 4

## Link to YouTube Demo video

https://www.youtube.com/watch?v=SbqKz1W62p0

---

### What are the main differences between a Docker image and a Docker container?

Ans) A Docker image is basically a template or blueprint that includes everything your app needs like the code, libraries, and dependencies. It’s immutable.

A container is what you get when you actually run that image. It’s the live, running version of your app based on the image. You can start, stop, or delete containers, but the image itself stays the same.

---

### Explain how Docker's layered architecture improves efficiency.

Ans) Docker builds images in layers, and each layer represents a change (like installing packages or adding files). The cool thing is that Docker reuses these layers instead of rebuilding everything from scratch each time.
This makes builds faster, saves disk space, and makes it easier to update or share images since only the changed layers need to be downloaded or rebuilt

---

### Why does each container get its own writable layer?

Ans) Each container gets its own writable layer so it can make changes (like writing logs or creating temporary files) without affecting other containers or the original image.
This way, containers stay isolated what happens inside one container doesn’t mess with another. Once you delete the container, that writable layer disappears too.

---

### What are the benefits of using Docker Compose over running containers individually?

Ans) Docker Compose is super helpful when your app needs more than one container (like a web app and a database). Instead of running each container one by one with long commands, you can just define everything in a single docker-compose.yml file.
Then you can start everything with one simple command docker-compose up. It’s easier, faster, and keeps your setup consistent every time you run it.

---
