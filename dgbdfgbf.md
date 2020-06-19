---
tags: [Authentication]
---

# Authentication

The "**fiwiPay**" API uses a "**Secret Key**" along with a "**Client Id**" in order to authenticate a merchant to then generate an "**access token**" which is used to access all other accessible routes within the fiwiPay platform.

The API secret key should not be made public and should be kept secure and therefore should not be placed in open repositories or client side code. All requests should be made over "**HTTPS**" to securely transmit the secret key to the fiwiPay platform.

In order to generate an **access token** a **POST** request should be submitted to the "**/api/v1/auth/token**" route with a **JSON** request body containing the "**client id**" and "**secret key**":

```json
{
  "client_id": "<merchant_client_id>",
  "client_secret": "<merchant_client_secret_key>"
}
```

The JSON response will contain the "**access_token**" which should be used as a "**Bearer**" token within an "**Authorization**" header to access all other endpoints made available within the fiwiPay platform.

```json
{
  "data": {
    "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwczpcL1wvcGF5bGF0YS5jb21cL2FwaVwvdjFcL2F1dGkhjfgdjhfcjhfcdkjufkhcL3Rva2VuIiwiaWF0IjoxNTc1MDA1NjYzLCJleHAiOjE1NzUwMDkyNjMsIm5iZiI6MTU3NTAwNTY2MywianRpIjoiWkRYQWhYZGRnYXRVVkl1dSIsInN1YiI6NCwikhfdcHJ2IjoiMjNiZDVjODkkjgdfku0OWY2MDBhZGIzOWU3MDFjNDAwODcyZGI3YTU5NzZmNyIsIm1lcmNoYW50X2lkIjo1LCJ1c2VyX2lkIjo0fQ.Uy9arGnRI8JrH1VpqGxDuYTZSx3fINe9NhAs-BR7E9I",
    "token_type": "bearer",
    "expires_in": 3600
  }
}
```
