---
title: Refresh -
method: POST
url: "{{CARTORIO_URL}}:/api/refresh"
---


Refresh - 

Faz o refresh do JWT token.


```request:cURL
curl --location --request POST "{{CARTORIO_URL}}/refresh" \
  --header "Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC8xMjcuMC4wLjE6ODAwMFwvYXBpXC9hdXRlbnRpY2FjYW8iLCJpYXQiOjE1OTEzODYxNDksImV4cCI6MTU5MTM4OTc0OSwibmJmIjoxNTkxMzg2MTQ5LCJqdGkiOiJSU0lzVVJhd1p3bktzbUR0Iiwic3ViIjoiOWI4OWJmNGUtYjJiMi00NWUwLTgyMWQtOWExZjIwOTA1ZDk3IiwicHJ2IjoiZTZkNjA2MDAwM2RkZDZkNzc5NjJjMDNjYjJiYjMyMjI5YmNlYTFjNSJ9.f1R3KbrIG8tFDc1BajkA4ntEKm2xI7Hj2i7_nNEMoUc" \
  --header "Content-Type: application/json" \
  --data ""
```


```response:200
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOlwvXC94cHRvLmxvY2FsaG9zdFwvYXBpXC9hdXRlbnRpY2FjYW8iLCJpYXQiOjE1OTA0NjI4NjEsImV4cCI6MTU5MDQ2NjQ2MSwibmJmIjoxNTkwNDYyODYxLCJqdGkiOiJkUFVMMVhMa1NUTmpkZ3J3Iiwic3ViIjoiYmRmYzJiMzYtOTNlZS00NTY1LTk2ZjYtZDVjZTFhMTRlNTI2IiwicHJ2IjoiYzAxMGM4OGUxMWY0MWM0Njc5YTNmMzVlMmQwYWQ3YTVlOWFiOWNkMCJ9.biV65aaiUeOnY21z-nV4577xF7F4oyRkaDgl-I59QvA",
  "token_type": "bearer",
  "expires_in": 3600
}

```


```response:401
{
  "status": "Token is Invalid"
}

```