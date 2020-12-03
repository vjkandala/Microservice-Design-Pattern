https://www.youtube.com/watch?v=uPndlp0kbok&list=PLq3uEqRnr_2EDsuxPboP9_WtVRR_TaMrF

Monolithic :

Easy to develop
Simple Testing
Easy to scale
Less Technicality 
Better to small scale apps

Disadvantages :

Limitation in size 
Long time to release new features
Even small change in one module needs to redeploy whole application 
no fault tolerance 
Reliability and availability 

Microservices : 

Advanges : 

Quick Response to change 
Increase uptime 
Loose coupling between services 
can experiement with any technology
Zero downtime

Disadvantages : 
communication between the services 
testing each service is challenge

Design Principles :

Independent/Autonomous - 
Fault Tolerant 
Observable - monitoring the services  
Discoverable - 
Domain Driven - Focus on Business, core domain and Domain logic
Decentralisation - Database for each services
High Cohesion - Each service need to do one thing - Single Resposibility principle (SRP ) 
Single source of Truth - 

Our Services :

Scalability 
Availabilty
Resilient to failures 

Patterns : 

Decomposition :  Design 

 1. Monolithic to microservices 
 2. Microservices from scratch 

a. Strangler Pattern : https://www.youtube.com/watch?v=9qfhb9rQ9Q8&list=PLq3uEqRnr_2EDsuxPboP9_WtVRR_TaMrF&index=6
   Account Services -> Order Service 
   
   Order service builded new microservice, now microservice we can route old monolithic and micro-service 
   
b. Sidekick or side car : https://www.youtube.com/watch?v=NQzZq9uRmtg&list=PLq3uEqRnr_2EDsuxPboP9_WtVRR_TaMrF&index=7

   Common features to take care for each service :
   
    Logging - Monitoring - Configuration - Proxy to remove service - Associate with application and attached to each application as sidecar

c. Service Mesh https://www.youtube.com/watch?v=u0-nWUL1I8g&list=PLq3uEqRnr_2EDsuxPboP9_WtVRR_TaMrF&index=8

   - This will come into picture when there are more services 
     - Communication complexity 
     - Failure Isolation 
     - Service Discovery 
     - Config changes

   - Its Dedicated infracture layer for service to service communication
   - Its way to control how different parts of an application share the data amoung themselves 
   - For cloud native application    
	

	 
   
Database : 

1. Database per service : 
    As names says Databse per service
	
	Pros : 
	Loosely Coupled

	Cons : 
	Queries that needs join over multiple db 
	transaction across multiple db
	
	Solution : 
	
	Queries needs join over multiple database
	
	CQRS
	Event Sourcing
	API Composition
	
	Transaction across multiple DB 
	
	Saga Pattern 
	
	BrownField Project - DB shared across multiple services, only max 2-3 services can share DB  

2. 	CQRS :  Command Query responsibilty Segregation

    Command - Create,update, Delete 
	Query - View 
	
	Product and Order services will seperate DB but for Query will have seperate DB 

3. Data Consistency - Has two parts : Eventual and Strong 
    
	https://www.youtube.com/watch?v=SI9Ocb691ps&list=PLq3uEqRnr_2EDsuxPboP9_WtVRR_TaMrF&index=12
	
	Eventual Consistency - Very fast responds to User 
	
	Strong - Provides acknowledge once all nodes(Db) replicated across nodes 

4. Event Driven Architecture : 

   Message Brokers - Kafka, Acive MQ, Rabbit MQ 

5. Event Sourcing System 

6. 2 Phase commit : 

   ACID - Atomicity, Consistency,Isolation and Durability 

   a. XA - Extended Architecture 
   b. Its pattern for distributed transaction
   c. ACID like global/distributed transaction processing
   d. Transaction Manager manages the transaction : 

        Prepare for commit or abort 
        perform the commit or abort 		
        		

 
Communication between Services 
Integration 
Deployment 
Observability 
Cross Cutting Concern 








