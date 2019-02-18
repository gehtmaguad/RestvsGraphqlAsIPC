# About
* The goal of this thesis is to evaluate REST and GraphQL as inter-process communication (IPC)
mechanism between microservices. For this purpose an existing project which already im-
plements a RESTful API is divided into three microservices with each of those microservices
fulfilling one particular task. These microservices are cloned and the REST API layer is re-
placed with a GraphQL API layer in order to form a second microservices architecture based
on GraphQL. Both architectures are then analyzed in respect to their performance and their
capabilities to perform schema validation. In addition Swagger and GraphiQL - which are the
most popular developer tools for RESTful APIs and GraphQL respectively - are investigated.
The outcomes show several interesting findings. In terms of performance GraphQLs query
capabilities can be a huge advantage compared to REST. While its overall response time is
slightly lower compared to the RESTful API, GraphQL especially outperforms REST in certain
cases as the number of necessary requests can be reduced significantly.
Another advantage of GraphQL is its type system which is used to validate the payload of
each request. In contrast REST as an architectural style does not specify any type system nor
any validation process. This thesis therefore uses Joi as external library to support validation
of payloads within a REST environment. The findings show that Joi can be used to implement
a conservative as well as a liberal validation strategy while GraphQL enforces a conservative
validation of the payloads. This has a major impact on microservices architectures due to
the reason that the conservative validation strategy enforces the payload to be conform with a
defined schema whereas the liberal validation strategy allows the payload to diverge from the
defined schema in order to fulfill the robustness principle. However, by modifying the GraphQL
library itself the thesis proofs that GraphQL can be adapted to enforce a liberal validation of the
payloads as well.
The investigation on the developer tools shows that Swagger as well as GraphiQL can be
used to auto generate a documentation for the developed APIs and to consume those APIs.
Swagger in addition also allows to set an authentication token in order to perform authenticated
requests while GraphiQL by default has no such option. Necessary changes to the GraphiQL
library are therefore performed in order to add support for authenticated requests to this library
as well.
