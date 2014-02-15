### MOTD

#### Retrieving MOTD information

This call returns information for the current MOTD (message of the day).

 Definition

    GET /api/v1/motd

 Example Request

```shell
$ curl -H 'Authorization: Bearer <your access token>' \
  'https://api-news.layervault.com/api/v1/motd'
```

 Example Response

```json
{
  "motd": {
    "downvote_count": 0,
    "message": "What was your first Mac? https://www.apple.com/30-years/your-first-mac/",
    "upvote_count": 6,
    "user_display_name": "Wells R.",
    "user_id": 272
  }
}
```

#### Upvoting an MOTD

This call upvotes the current MOTD.

Definition

    POST /api/v1/motd/upvote

 Example Request

```shell
$ curl -H 'Authorization: Bearer <your access token>' \
  -X POST \
  'https://api-news.layervault.com/api/v1/motd/upvote'
```

 Example Response

```json
{
  "motd": {
    "downvote_count": 0,
    "message": "What was your first Mac? https://www.apple.com/30-years/your-first-mac/",
    "upvote_count": 7,
    "user_display_name": "Wells R.",
    "user_id": 272
  }
}
```

#### Downvoting an MOTD

This call downvote the current MOTD.

Definition

    POST /api/v1/motd/downvote

 Example Request

```shell
$ curl -H 'Authorization: Bearer <your access token>' \
  -X POST \
  'https://api-news.layervault.com/api/v1/motd/downvote'
```

 Example Response

```json
{
  "motd": {
    "downvote_count": 1,
    "message": "What was your first Mac? https://www.apple.com/30-years/your-first-mac/",
    "upvote_count": 6,
    "user_display_name": "Wells R.",
    "user_id": 272
  }
}
```