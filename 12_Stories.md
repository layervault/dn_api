### Stories

#### Retrieving Story Information

This call returns information for a story.

 Definition

    GET /api/v1/stories/:id

 Example Request

    $ curl -H 'Authorization: Bearer <your access token>' 'https://api.news.layervault.com/api/v1/stories/:id'

 Example Response

```json
{
  "story": {
    "comment": "",
    "comments": [
        ...
    ],
    "created_at": "2014-01-24T17:15:19Z",
    "id": 13627,
    "site_url": "http://localhost:3000/stories/13627-a-logo-should-tell-a-story",
    "title": "A logo should tell a story.",
    "url": "http://localhost:3000/click/stories/13627",
    "vote_count": 11
  }
}
```

#### Retrieving the front page

This call will returns a list of stories on the set page. **Note:** Page numbering starts at `1`.
If not specified, the default page will be `1`.

 Definition

    GET /api/v1/stories

 Example Request

    $ curl -H 'Authorization: Bearer <your access token>' 'https://api.news.layervault.com/api/v1/stories'

 Example Response

```json
{
  "stories": [
    {
      "comment": "",
      "comments": [
          ...
      ],
      "created_at": "2014-01-24T17:15:19Z",
      "id": 13627,
      "site_url": "http://localhost:3000/stories/13627-a-logo-should-tell-a-story",
      "title": "A logo should tell a story.",
      "url": "http://localhost:3000/click/stories/13627",
      "vote_count": 11
    }
  ]
}
```

#### Upvoting a Story

This call will upvote a Story on a user's behalf. This can only be called once per user.
Abuses of upvoting will get your app banned.

 Definition

    POST /api/v1/stories/:id/upvote

 Example Request

    $ curl -X POST -H 'Authorization: Bearer <your access token>' 'https://api.news.layervault.com/api/v1/stories/13627/upvote'

 Example Response

```json
{
  "story": {
    "comment": "",
    "comments": [
        ...
    ],
    "created_at": "2014-01-24T17:15:19Z",
    "id": 13627,
    "site_url": "https://news.layervault.com/stories/13627-a-logo-should-tell-a-story",
    "title": "A logo should tell a story.",
    "url": "https://news.layervault.com/click/stories/13627",
    "vote_count": 12
  }
}
```
