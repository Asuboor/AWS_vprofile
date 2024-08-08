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

![Screenshot (243)](https://github.com/user-attachments/assets/a37682fb-e9cb-4deb-bd98-3d5d56b8b1b1)



### Step 2: CDN Image Delivery with CloudFront

- **CloudFront** ensures fast delivery of CDN images, caching them at edge locations close to users for reduced latency and improved performance.

![Screenshot (255)](https://github.com/user-attachments/assets/1fca4331-fd8d-44de-b3f0-da2a0694f301)

### Step 3: Elastic Beanstalk Application Load Balancer Routing 

- **Application Load Balancer** routes incoming HTTP requests to any available EC2 instance running Apache Tomcat.

![Screenshot (251)](https://github.com/user-attachments/assets/fd244cc6-f97d-4ae8-bad0-b7ea825f9d04)
![Screenshot (252)](https://github.com/user-attachments/assets/b5745c56-bc60-48c6-82cd-006888403b9f)


### Step 4: Apache Tomcat Hosting

- **EC2 Instances** run Apache Tomcat to host the VProfile Java application, providing a scalable and reliable environment for Java web applications.

![Screenshot (244)](https://github.com/user-attachments/assets/75e638ab-e6fd-426d-a3a3-856fdad25399)

### Step 5: Monitoring with Amazon CloudWatch

- **CloudWatch** monitors EC2 instances, Apache Tomcat performance metrics, and application logs.
- Auto Scaling policies are configured based on CloudWatch metrics:
  - **Network Out High**: Automatically scales up to a maximum of 3 instances during high traffic.
  - **Minimum Availability**: Ensures a minimum of 2 instances are always available for redundancy and performance.

![Screenshot (254)](https://github.com/user-attachments/assets/2571c9fc-507e-40ae-a379-b5dd9a5a260d)

### Step 6: Amazon MQ Integration

- **Amazon MQ** serves as a message broker for the VProfile application, enabling reliable communication between different components and services.

![Screenshot (249)](https://github.com/user-attachments/assets/3605e8ad-0f69-4979-b104-bc44182f2a27)

### Step 7: ElastiCache and Amazon RDS Integration

- **ElastiCache (Memcached)** is integrated with **Amazon RDS (MySQL)**:

![Screenshot (247)](https://github.com/user-attachments/assets/f7705d1b-7e4f-4dee-a744-247979b278b7)

- **ElastiCache** caches frequently accessed data from **Amazon RDS** using Memcached, reducing database load and improving response times.

![Screenshot (248)](https://github.com/user-attachments/assets/ca832467-4a10-41d4-b5ad-96e3a5f48a55)
[From Database]
![Screenshot (245)](https://github.com/user-attachments/assets/109b385b-3c9e-466d-9e68-a6ba9a569f56)
[From Cache]
![Screenshot (246)](https://github.com/user-attachments/assets/d11cbd07-3d27-4f1e-b805-85561b1318dc)

### Step 8: Artifact Storage in S3

- Application artifacts, including Java application code and configuration files, are stored in **Amazon S3** buckets.
- **S3** ensures secure and scalable storage, enabling easy retrieval and deployment of application artifacts.

## Deployment and Management

- **Deployment**: Use Git Bash or AWS Management Console to deploy application artifacts to S3 and update the Elastic Beanstalk environment.
- **Monitoring and Scaling**: Monitor application performance and scale resources using CloudWatch alarms and Auto Scaling policies.
- **Maintenance and Updates**: Regularly update application code and configurations stored in S3, ensuring smooth operation and security patches.

## Conclusion

This AWS infrastructure setup provides a scalable, reliable, and high-performance environment for hosting the VProfile Java application. By leveraging AWS services like CloudFront, EC2, Auto Scaling, Amazon MQ, ElastiCache, RDS, and S3, the application achieves optimal performance, low latency, and high availability for its users.
