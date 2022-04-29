# Load Balancers Deep Dive

## What is a Load Balancer?
Distributes network traffic across backend systems
Health checks ensure only healthy backend systems get traffic
2 Types: Application and Network Load Balancer
Application. Layer 7 routing, Intelligent routing
Network. Layer 4 routing. Fast 🔥


## How do Load Balancers Work?
Distributes network traffic across backend systems
Health checks ensure only healthy backend systems get traffic
2 Types: Application and Network Load Balancer
Application. Layer 7 routing, Intelligent routing
Network. Layer 4 routing. Fast 🔥


## Why Do They Matter?


## Targets
Where the load balancer sends traffic? 
Virtual Machines (EC2 instances)
Containers (Elastic Kubernetes Service – EKS, Elastic Container Service – ECS)
Lambda functions (Function as a Service)
Auto-scaling group
IP address


## Algorithms
How does the load balancer know which server to send traffic to? 
Routing Algorithms (Methods)
Round Robin 
Weighted round robin
Least connections
Least response time
Others


## State Management
How do load balancers know which servers have traffic?
Maintains an internal table of connections
Client IP
Destination IP (LB virtual IP)
Source Port (1-65535)
Destination Port (1-65535). Typically port 80 (HTTP) or 443 (HTTPS) for web traffic
IP protocol. TCP/UDP
Can now support sticky sessions (sending to the same server), and “least connections” algorithms, and more



## Layer 7 Routing
Can route traffic based on the URL path
Requires Application load balancer (Layer 7 routing)
Assign target groups to different paths
Routes in real-time

## Layer 4 Routing

## High Availability in AWS
Application Load Balancers
Spread over multiple availability zones (AZ – one or more data centers)
Cross-zone routing enabled by default
Load balancer node placed in each AZ
Uses Reverse Proxy to target VM’s/containers in that AZ
X-FORWARDED-FOR HTTP header contains origination client IP address


## Authentication
Supports authentication for added security
Integrates with Cognito or IAM (Identity groups)


## Global Server Load Balancing (GSLB)
Uses Domain Name Service (DNS) to share load across geographic locations
Increases availability and localization 
In AWS, use DNS Route53 multi-response routing policy to mimic round robin
Lacks advanced features of dedicated load balancers
Demo!

