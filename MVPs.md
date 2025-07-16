For each MVP a video would be make to describe that

🔐 MVP 1 – Secure Auth Flow via Keycloak, LDAP & Vault
This MVP demonstrates a full secure login flow:

Frontend: Postman (or later Web UI)

Auth Provider: Keycloak

User Directory: OpenLDAP

Secret Storage: Vault (AppRole auth)

Token Format: JWT (RS256, asymmetrically signed)

🔄 Flow Overview:
POST /realms/{realm}/protocol/openid-connect/token

LDAP verification → JWT creation → Vault public key storage

Role-based access token returned to client

✅ This proves the integration of IAM, secret management, and token-based security.
