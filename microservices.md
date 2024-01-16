[Refer link https://learn.microsoft.com/en-us/azure/architecture/guide/architecture-styles/microservices](https://learn.microsoft.com/en-us/azure/architecture/guide/architecture-styles/microservices)

[Refer link https://cloudacademy.com/blog/microservices-architecture-challenge-advantage-drawback/](https://cloudacademy.com/blog/microservices-architecture-challenge-advantage-drawback/)

## Advantages of microservices

1. **Agility**

   - Because microservices are deployed independently, it's easier to manage bug fixes and features release. You can update a service without redeploying the entire application, and roll back an update if something goes wrong.
   - In many traditional applications, if a bug is found in one part of the application, it can block the entire release process. New features might be held up waiting for a bug fix to be integrated, tested, and published.
2. **Small, focused teams**

   - A microservice should be small enough that a single feature team can build, test, and deploy it. Small team sizes promote greater agility. Large teams tend be less productive, because communication is slower, management overhead goes up, and agility diminishes.
3. **Small code base**

   - In a monolithic application, there is a tendency over time for code dependencies to become tangled. Adding a new feature requires touching code in a lot of places. By not sharing code or data stores, a microservices architecture minimizes dependencies, and that makes it easier to add new features.
   - Smaller codebases and scope = quicker deployments, which also allow you to start to explore the benefits of Continuous Deployment.
   - Ease of understanding: With added simplicity, developers can better understand the functionality of a service.
4. **Mix of technologies**

   - Teams can pick the technology that best fits their service, using a mix of technology stacks as appropriate.
   - Eliminate vendor or technology lock-in : Microservices provide the flexibility to try out a new technology stack on an individual service as needed. There won’t be as many dependency concerns and rolling back changes becomes much easier. With less code in play, there is more flexibility.
5. Fault isolation

   - If an individual microservice becomes unavailable, it won't disrupt the entire application, as long as any upstream microservices are designed to handle faults correctly. For example, you can implement the [Circuit Breaker pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/circuit-breaker), or you can design your solution so that the microservices communicate with each other using [asynchronous messaging patterns](https://learn.microsoft.com/en-us/dotnet/architecture/microservices/architect-microservice-container-applications/asynchronous-message-based-communication).
   - Larger applications can remain mostly unaffected by the failure of a single module.
6. **Scalability**

   - Services can be scaled independently, letting you scale out subsystems that require more resources, without scaling out the entire application. Using an orchestrator such as Kubernetes or Service Fabric, you can pack a higher density of services onto a single host, which allows for more efficient utilization of resources.
7. **Data isolation**

   - It is much easier to perform schema updates, because only a single microservice is affected. In a monolithic application, schema updates can become very challenging, because different parts of the application might all touch the same data, making any alterations to the schema risky.

## Disadvantages of microservices

1. **Complexity**

   - A microservices application has more moving parts than the equivalent monolithic application. Each service is simpler, but the entire system as a whole is more complex.
2. **Development and testing**

   - Writing a small service that relies on other dependent services requires a different approach than writing a traditional monolithic or layered application. Existing tools are not always designed to work with service dependencies. Refactoring across service boundaries can be difficult. It is also challenging to test service dependencies, especially when the application is evolving quickly.
3. **Lack of governance**

   - The decentralized approach to building microservices has advantages, but it can also lead to problems. You might end up with so many different languages and frameworks that the application becomes hard to maintain. It might be useful to put some project-wide standards in place, without overly restricting teams' flexibility. This especially applies to cross-cutting functionality such as logging.
4. **Network congestion and latency**

   - The use of many small, granular services can result in more interservice communication. Also, if the chain of service dependencies gets too long (service A calls B, which calls C...), the additional latency can become a problem. You will need to design APIs carefully. Avoid overly chatty APIs, think about serialization formats, and look for places to use asynchronous communication patterns like [queue-based load leveling](https://learn.microsoft.com/en-us/azure/architecture/patterns/queue-based-load-leveling).
5. **Data integrity**

   - With each microservice responsible for its own data persistence. As a result, data consistency can be a challenge. Embrace eventual consistency where possible.
6. **Management**

   - To be successful with microservices requires a mature DevOps culture. Correlated logging across services can be challenging. Typically, logging must correlate multiple service calls for a single user operation.
7. **Versioning**

   * Updates to a service must not break services that depend on it. Multiple services could be updated at any given time, so without careful design, you might have problems with backward or forward compatibility.
8. **Skill set**

   - Microservices are highly distributed systems. Carefully evaluate whether the team has the skills and experience to be successful.
9. **More services equals more resources**

   - Multiple databases and transaction management can be painful.

## Microservices use cases

[Refer link: https://www.shopify.com/enterprise/disadvantages-microservices](https://www.shopify.com/enterprise/disadvantages-microservices)

* **Real-time data processing and analysis**. Microservices can handle real-time data processing and analysis, providing insights faster.
* **Batch processing**. By breaking down the task into smaller independent services, you can process multiple batches simultaneously.
* **Load balancing**. Microservices enable load balancing by scaling up only the services that experience heavy traffic, which is more resource-efficient.
* **Machine learning.** Different models or different parts of a model can be deployed as individual services, making the system more manageable and scalable.
* **Internet of Things (IoT)**. Microservices can help handle this IoT data effectively by dividing tasks among multiple services.

## Is It Right for Your Project?

[Refer link https://identio.fi/en/blog/the-pros-and-cons-of-microservices-is-it-right-for-your-project/](https://identio.fi/en/blog/the-pros-and-cons-of-microservices-is-it-right-for-your-project/)


Keep in mind, you can always go microservice later, and there is no one telling you you cannot mix and match.  ***Use the tools that work best for your needs*** .

Here are some general tips I think one should always follow when building software, regardless of the architecture:

1. Modularize your code: Even though you are using a monolithic architecture, it’s important to write modular code that can be easily broken down into smaller services in the future. This can involve breaking down your code into separate components or modules that can be decoupled later on.
2. Use standard interfaces: To ensure that your code can be easily integrated with other services in the future, it’s essential to use standard interfaces and protocols for communication. This can involve using RESTful APIs, message queues, or other communication protocols that can be easily integrated with other services.
3. Separate business logic from presentation logic: To ensure that your code can be easily reused in a microservices architecture, it’s important to separate your business logic from your presentation logic. This can involve separating your code into different layers, such as a data access layer, a business logic layer, and a presentation layer.
4. Use containerization: Containerization is a way of packaging software in a format that can run consistently across different environments. By using containerization, you can ensure that your monolithic application can be easily broken down into smaller services later on.
5. Use monitoring and logging: Monitoring and logging can help you identify performance issues and bottlenecks in your monolithic architecture. By monitoring your application, you can iden
