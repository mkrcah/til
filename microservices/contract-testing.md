## Testing integrations with contract testing, as a trade-off between unit tests and integration tests

How to test integrations between services?

Common approaches are:
- Do nothing, skip these types of tests 
- Automated integration/end-to-end tests
- Manual tests

One problem with automated integration/end-to-end tests is that these might be harder to setup, might take longer and the dev 
experience might take a hit. 

Unit-tests, on the contrary, are typically fast, isolated, with ergonomic dev experience.  

Contract tests are a way to get test quality closer to integration tests while using unit-test approach.

Example:  

- Given an API server (producer), and an API client (consumer), the contract could be a set of json files with an example HTTP request & response, stored in a location accessible by both the producer and the consumer.  
- There’s a test on the consumer part, which mocks the request and the response, and tests the functionality of the consuming service.
- Similarly, there’s a test on the producer part, which ensures the server produces the example response given the example request.

Read more at [Building Microservices](https://www.amazon.com/Building-Microservices-Designing-Fine-Grained-Systems/dp/1491950358) - chapter Consumer-Driven Tests to the Rescue

UPDATE: There are SaaS solutions for contract testing, for example, [Pact](https://pact.io/)
