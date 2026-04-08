OAuth2 & Keycloak (Spring Boot) 

  - Implémentation de l’authentification avec OAuth2 / OpenID Connect
  - Configuration de Keycloak comme Authorization Server
  - Sécurisation des API Spring Boot avec validation des tokens
  - Gestion des access tokens et refresh tokens
  - Implémentation du RBAC (Role-Based Access Control)
  - Intégration du social login (GitHub)

🔄 Auth Flow
sequenceDiagram
    participant Client (Angular / Postman)
    participant Keycloak
    participant API (Spring Boot)

    Client->>Keycloak: Authentication (username/password or social login)
    Keycloak-->>Client: Access Token (JWT)

    Client->>API: Request + Bearer Token
    API->>Keycloak: Token validation (public key / introspection)
    API-->>Client: Protected resource
