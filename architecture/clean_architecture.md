## Clean Architecture

The design of all relevant microservices follows the Clean Architecture pattern. This helped us in maintaining a core domain design that abstracts away from all technical issues. As showed in the picture above, we made use of the following layers:

-   **Domain**: DDD entities, value objects, factories, ...
-   **Application**: DDD services, repositories, ...
-   **Presentation**: Machinery to translate external data representation to domain entities and vice versa.
-   **Infrastructure**: Mostly external service implementation, DB interfaces, REST APIs, Events managers, ...

[Documentation](https://revue-org.github.io/revue/docs/report/design/architecture/microservices#clean-architecture)
