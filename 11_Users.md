### User Information

#### Retrieving User Information

This call returns the user information for which the Client is acting on behalf of.

 Definition

    GET /api/v1/me

 Example Request

    $ curl -H 'Authorization: Bearer <your access token>' 'https://api-news.layervault.com/api/v1/me'

 Example Response

```json
{
  "me": {
    "created_at": "2012-11-15T04:48:45Z",
    "first_name": "Kelly",
    "job": "Founder at LayerVault",
    "last_name": "Sutton",
    "portrait_url": "https://news.layervault.com/cats.gif"
  }
}
```