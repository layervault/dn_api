## Authentication and Requesting Access Tokens

All endpoints require authentication of some form.

### GET Endpoints

GET endpoints do not require user authentication, but they do require at the least application authentication. This means that either an OAuth client ID or a user access token must be present. To make a request with a client ID, simply send it as a GET parameter, like this:

``` shell
curl https://api-news.layervault.com/api/v1/stories?client_id=91a5fed537b58c60f36be1sdf71ed1320e9e4af2bda4366f7dn3d79e63835278
```

### POST requests

All API POST requests are required to be user authenticated via an oAuth 2 access token. It's easy to request a token via the command line to get a feel for how things work:

```shell
curl -i https://api-news.layervault.com/oauth/token \
  -F grant_type="password" \
  -F username="<your Designer News username>" \
  -F password="<your Designer News password>" \
  -F client_id="<client_id_goes_here>" \
  -F client_secret="<client_secret_goes_here>"
```

Which will return an Access token response like this one:

```json
{
  "access_token":"aec9c670cf5e673bfedf83d055d2a2e0e5f37e52d3b41cffcf7874f73a7458bf",
  "token_type":"bearer",
  "scope":"user"
}
```

The access token must then be passed in the Authorization header for all POST requests. See examples below for more information.
