For each MVP a video would be make to describe that

🎯 Functional Goal:
An authenticated user sends a request (e.g., to create a team) via JWT.

The system:

Validates the JWT using a public key securely stored in Vault

Routes the request through NGINX → Gravitee Gateway

Gravitee uses Consul for service discovery

Nomad handles orchestration of the backend service

Observability is enabled with OpenTelemetry, Jaeger, Serilog → Graylog, Prometheus → Grafana


🚀 MVP 1 – Authentication via Keycloak + OpenLDAP + Vault
Scenario:

The user sends a login request to Keycloak (via Postman or frontend).
Keycloak validates the credentials against OpenLDAP.

If credentials are valid, Keycloak generates a JWT token.

Keycloak pushes the public key (used for JWT signature) into Vault (for microservices to use).

The token is sent back to the user based on their role (admin, manager, standard user).

🔄 Flow Overview:
POST /realms/{realm}/protocol/openid-connect/token

✅ This proves the integration of IAM, secret management, and token-based security.

📦 Stack:

Keycloak with LDAP identity federation

OpenLDAP as authentication source

Vault to securely store the JWT public key

Asymmetric JWT authentication (RS256)

| Project | Description | Demo Video | Status |
|--------|-------------|------------|--------|
| 🔐 **MVP 1 – Auth Flow with Vault Integration** | User logs in via Keycloak (OpenLDAP backend).



🚀 MVP 2 – Secure API Access with JWT + Vault
Scenario:

The client sends a POST /teams request to Team-Microservice with the JWT token.

The microservice uses a custom NuGet package (CustomVaultPackage) to fetch the JWT public key from Vault.

It validates the token using the public key.

If valid, and the user is authorized, a team is created.

📦 Stack:

Team-Microservice (.NET 8)

Vault (AppRole + policy for secure read)

Private NuGet (via Nexus) for the Vault package

JWT signature validation per microservice

| Project | Description | Demo Video | Status |
|--------|-------------|------------|--------|
| 🔑 **MVP 2 – Secure API Call with JWT Validation** | The client sends a request with a JWT. The service uses a Vault-integrated NuGet package to verify the token. | [🎥 Secure API Demo](https://youtu.be/demo-link) |Not Yet |


🚀 MVP 3 – NGINX → Gravitee Gateway → Consul → Nomad
Scenario:

Client sends the request to NGINX, acting as the first reverse proxy.

NGINX forwards the request to the Gravitee Gateway.

Gravitee uses Consul to:

Dynamically discover available backend services

Register new services in its internal routing table

Gravitee forwards the request to the right backend service (e.g., Team-Microservice) running on Nomad.

📦 Stack:

NGINX for entry point

Gravitee.io as API Gateway

Consul for service registration/discovery

Nomad for workload orchestration


| Project | Description | Demo Video | Status |
|--------|-------------|------------|--------|
| 🔁 **MVP 3 – Reverse Proxy to Gateway to Backend** | Request flow: NGINX → Gravitee Gateway → Consul (discovery) → Nomad-orchestrated microservice. | [🎥 Routing Demo](https://youtu.be/demo-link) | 🛠️ In Progress |


🚀 MVP 4 – Observability: Tracing, Logging, Metrics
Scenario:

An API request is initiated to Team-Microservice.

OpenTelemetry automatically traces the request end-to-end.

Traces are sent to Jaeger for distributed analysis.

Serilog logs are pushed to Graylog (via Serilog Sink).

Prometheus scrapes metrics exposed by each container.

Grafana displays:

Success/failure rates

Request latency

Service health

📦 Stack:

OpenTelemetry SDK (.NET)

Jaeger for traces

Serilog → Graylog

Prometheus → Grafana

Docker Compose + Nomad metrics exporters

| Project | Description | Demo Video | Status |
|--------|-------------|------------|--------|
| 🔍 **MVP 4 – Full Observability Layer** | Live tracing (Jaeger), logging (Graylog), and metrics (Prometheus to Grafana) for all service calls. | [🎥 Observability Demo](https://youtu.be/demo-link) | 🛠️ In Progress |

