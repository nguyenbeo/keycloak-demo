# keycloak-demo
A demo to show how to use Keycloak as IAM application

## Prerequisites
* Docker / Docker compose

## Some Admin Client tests
### How to start Keycloak locally
```
```
### Get token for admin user
```
curl \
  -d "client_id=admin-cli" \
  -d "username=admin" \
  -d "password=Pa55w0rd" \
  -d "grant_type=password" \
  "http://localhost:8080/auth/realms/master/protocol/openid-connect/token"
```

### Get user from another Realm
* Replace {access_token} with access_token from json response above
* Replace {realm} that you created in Keycloak
```
curl \
  -H "Authorization: bearer {access_token}" \
  "http://localhost:8080/auth/admin/realms/{realm}/users/{user_id}"
```

### Get role mappings for the user
* Replace {access_token} with access_token from json response above
* Replace {realm} that you created in Keycloak
* Replace {user_id} with Keycloak User Id
```
curl \
  -H "Authorization: bearer {access_token}" \
  "http://localhost:8080/auth/admin/realms/{realm}/users/{user_id}/role-mappings"
```
