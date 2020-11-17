Monolithic - 

Restricted to technology stack.
Engineering team can't focus on one module.
DB scalability- we can add read replicas but adding write replicas is a problem.
Overloaded VM/containers.
CI/CD  build take more time for a big monolith.
Code understanding is difficult.


++++++++ Microservices +++++++++++

	Scaling, deploy easy
	technology easing and adaptablity to new stacks

Cons - 

	  Interprocess communication
	  Transactions are distributed like two phased commit, saga
	  more resources
	  debugging issues.


Scaling ways - 

	Horizontal scaling
	Data partioning - partition data to be handled by different servers.
	Functional decomposition

  ![Screenshot](micro_scale_cube.png)


API Gateway ====> 

	As direct calls to multiple services will incur more time and resource consumption.

BFF (Backend for Frontend) ====> 

	This means diff. gateway for different types like
	1-  API Gateway for web 
	2 - API Gateway for mobile
	3 - API Gateway for 3rd party(exposing ur own API)


Uses of API Gateway ====> 
	
	Authentication - Token based
	SSL Termination like Nginx
	Load Balancing
	Insulation - By using VPC to keep services.

	Other pros -
	API health monitoring
	Caching
	Authorization
	API versioning
	A/B tesing 

Cons -

	Added latency because of mediator i.e, Gateway
	More complex and extra resource.


Service Registry ====> 

	To keep track of network address details of all services for communication b/w gateway and services or inter-services

Ways for Registry -

	Registering itself whenever some new instance is added or go down.
	Service Registry  will ask service based on events related to cluster up/down and ask that service for updated cluster details.

InterService Communication - 

	Syncronous communication - Communicating updates to other microservices. Ex: using REST, gRPC
						AG ---> M1 ---> M2

	Asynchronous communication(Event/Message Driven) - Communicating using queues to other services asynchronously. Use pub/sub pattern. Ex: using Kafka

			AG  |---|  M1 	 |---|  M2
					   |__   |---|  M3
		More faster and no need for service discovery.








