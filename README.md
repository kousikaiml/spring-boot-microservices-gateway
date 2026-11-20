# Spring Boot Microservices Gateway
A Java 17 / Spring Cloud Gateway portfolio demo with route configuration, request correlation IDs,
JWT-style HMAC token validation for a protected route, Resilience4j circuit breaker fallback, and
rate limiting configuration.

## Run
Requires Java 17 and Maven. Start two mock services in separate terminals:
`python mock_services/catalog.py` and `python mock_services/orders.py`.
Then run `mvn spring-boot:run`. Gateway: http://localhost:8080.
Try `curl http://localhost:8080/catalog/products` and
`python generate_demo_token.py` to print the local demo token, then call `curl -H "Authorization: Bearer PASTE_TOKEN_HERE" http://localhost:8080/orders/private`.

The token example is intentionally a learning placeholder; use an identity provider, asymmetric
signatures, key rotation, TLS, external secrets, and distributed rate-limit storage in production.
The routes are configured for local mock services at ports 8081 and 8082.
"# spring-boot-microservices-gateway" 
