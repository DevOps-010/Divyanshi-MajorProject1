# Divyanshi-MajorProject1
Setting up local environment using virtualBox and Vagrant

- Virtual box: used to create virtual machines
- vagrant: enables automation and management of multiple virtual machines through code

This project focuses on deploying a java based application that relies on 5 key servers: MySQL, Memcache, Tomcat, RabbitMQ, Nginx.
- Nginx: web server used for serving websites, load balancingand handling http requests efficiently.
- Tomcat: used as web servers for java applications. It allows execution of dynamic web content, processing client requests and serving java servlet.
- Memcache: a key-value store used to speed up dynamic web applications. It caches frequently accessed data reducing the database load and increasing performance.
- MySQL: a relational database managemnet system that uses structured query language to store, manage and retrieve data in a structured format.
- RabbitMQ: message broker that allows communication between applications/ systems. It allows the applications to send messages to a queue. This asynchronous communication enhances readability, scalability and performance.

Project Flow:


<img width="703" alt="Screenshot 2025-05-16 at 12 01 59 AM" src="https://github.com/user-attachments/assets/a05658e7-6fbe-4396-a916-7c2381fdfeb5" />

- user accesses application through a web based login page.
- request goes to nginx, a load balancer, that forwards it to an available tomcat server for processing.
- tomcat recieves the request and first checks with memcache.
- memcache sees if the user's sśsions/ credentials are already there.
- if not, it forwards the request to MySQL server that is the primary database.
- after handling authentication, tomcat sends message to RabbitMQ.
- it queues tasks like logging user activity or sending login notifications and any authorised consumer of RabbitMQ can pick these messages and process them accordingly.

Why this architechture?
- Scalability
- Performance optimisation
- Reliable communication
