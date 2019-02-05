# Gotifier
A notification service written in Go.


# Hosted
Fill in the settings file (slack token etc)

# Cloud based
Make a request to the `/authentication/slack` endpoint, with the below payload. This will then return a JWT, with the specified expiry time, for you to use in your notification requests so you don't have to pass your token every time. 

`refreshInterval` will, if set, check the expiry of the JWT on every request and, if there is less time than the refreshInterval, will send another token through in a `x-auth-token` header with the expiry set to the `expiry` setting originally passed through. 

```json
{
  "token": "",
  "expiry": "20m",
  "refreshInterval": "5m" 
}
```
