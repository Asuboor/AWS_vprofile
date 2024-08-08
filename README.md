# AWS Infrastructure Setup for VProfile Java Application

## Overview

This project sets up a robust AWS infrastructure to host and manage the VProfile Java application. The architecture ensures scalability, high availability, and efficient performance through various AWS services.

## Technologies Used

- **VProfile Java Application**: Core application developed in Java, deployed on Apache Tomcat.
- **Amazon CloudFront**: Content Delivery Network (CDN) for fast and secure delivery of static and dynamic content.
- **AWS Application Load Balancer**: Distributes incoming application traffic across multiple instances running Apache Tomcat.
- **Amazon EC2 Instances**: Virtual servers running Apache Tomcat to host the Java application.
- **Amazon CloudWatch**: Monitors AWS resources and applications, providing real-time monitoring and alerting.
- **Auto Scaling**: Automatically adjusts the number of EC2 instances based on traffic and application load.
- **Amazon MQ**: Managed message broker service for reliable communication between application components.
- **Amazon ElastiCache (Memcached)**: In-memory caching service to improve application performance by caching frequently accessed data.
- **Amazon RDS (MySQL)**: Managed relational database service to store application data securely and reliably.
- **Amazon S3**: Object storage service used to store and retrieve application artifacts.

## Detailed Setup and Working Steps

### Step 1: Website Access via Load-Balanced URL

Users access the VProfile Java application via a load-balanced URL provided by the AWS Application Load Balancer.

### Step 2: CDN Image Delivery with CloudFront

- **CloudFront** ensures fast delivery of CDN images, caching them at edge locations close to users for reduced latency and improved performance.

### Step 3: Application Load Balancer Routing

- **Application Load Balancer** routes incoming HTTP requests to any available EC2 instance running Apache Tomcat.

### Step 4: Apache Tomcat Hosting

- **EC2 Instances** run Apache Tomcat to host the VProfile Java application, providing a scalable and reliable environment for Java web applications.

### Step 5: Monitoring with Amazon CloudWatch

- **CloudWatch** monitors EC2 instances, Apache Tomcat performance metrics, and application logs.
- Auto Scaling policies are configured based on CloudWatch metrics:
  - **Network Out High**: Automatically scales up to a maximum of 4 instances during high traffic.
  - **Minimum Availability**: Ensures a minimum of 2 instances are always available for redundancy and performance.

### Step 6: Amazon MQ Integration

- **Amazon MQ** serves as a message broker for the VProfile application, enabling reliable communication between different components and services.

### Step 7: ElastiCache and Amazon RDS Integration

- **ElastiCache (Memcached)** is integrated with **Amazon RDS (MySQL)**:
  - **ElastiCache** caches frequently accessed data from **Amazon RDS** using Memcached, reducing database load and improving response times.

### Step 8: Artifact Storage in S3

- Application artifacts, including Java application code and configuration files, are stored in **Amazon S3** buckets.
- **S3** ensures secure and scalable storage, enabling easy retrieval and deployment of application artifacts.

## Deployment and Management

- **Deployment**: Use Git Bash or AWS Management Console to deploy application artifacts to S3 and update the Elastic Beanstalk environment.
- **Monitoring and Scaling**: Monitor application performance and scale resources using CloudWatch alarms and Auto Scaling policies.
- **Maintenance and Updates**: Regularly update application code and configurations stored in S3, ensuring smooth operation and security patches.

## Conclusion

This AWS infrastructure setup provides a scalable, reliable, and high-performance environment for hosting the VProfile Java application. By leveraging AWS services like CloudFront, EC2, Auto Scaling, Amazon MQ, ElastiCache, RDS, and S3, the application achieves optimal performance, low latency, and high availability for its users.
