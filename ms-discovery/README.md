# RegistrationSystemMicroservices

The goal is to build a registration system that will send a confirmation mail after a new user is registered.\

1. **Service registry(Eureka)**: where all services will register themselves.
2. **Config server (Spring Cloud Config)**: where all services will take their configurations from. Config server will 
keep configuration files in git repository
3. **Gateway (Zuul)**: that will redirect all the request to the needed microservice
4. **User service**: using this one the new users will register. On every new registration the User service will send a 
message "USER_REGISTERED" to the message broker (Kafka)
5. **Email service**: using this one we will send emails. On "USER_REGISTERED" message received the Email service will send
a confirmation email to the new user.