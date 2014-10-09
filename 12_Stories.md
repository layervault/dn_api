### Stories

#### Retrieving Story Information

This call returns information for a story.

 Definition

    GET /api/v1/stories/:id

 Example Request

```shell
$ curl 'https://api-news.layervault.com/api/v1/stories/:id?client_id=abc123'
```

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
    "vote_count": 11,
    "sponsored": false
  }
}
```

#### Retrieving the front page

This call returns a list of stories on the set page. **Note:** Page numbering starts at `1`.
If not specified, the default page will be `1`.

 Definition

    GET /api/v1/stories

 Example Request

```shell
$ curl 'https://api-news.layervault.com/api/v1/stories?client_id=abc123'
```

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
      "vote_count": 11,
      "sponsored": false
    },
    ...
  ]
}
```

#### Retrieving recent stories

This call returns the content of the most [Designer News recent stories](https://news.layervault.com/new), offset
by a `page` number. **Note:** Page numbering starts at `1`. If not specified, the default page will be `1`.

 Definition

    GET /api/v1/stories/recent

 Example Request

```shell
$ curl 'https://api-news.layervault.com/api/v1/stories/recent?client_id=abc123'
```

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
      "vote_count": 11,
      "sponsored": false
    },
    ...
  ]
}
```

#### Upvoting a Story

This call will upvote a Story on a user's behalf. This can only be called once per user.
Abuses of upvoting will get your app banned.

 Definition

    POST /api/v1/stories/:id/upvote

 Example Request

```shell
$ curl -X POST -H 'Authorization: Bearer <your access token>' \
  'https://api-news.layervault.com/api/v1/stories/13627/upvote'
```

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
    "vote_count": 12,
    "sponsored": false
  }
}
```

#### Commenting on a Story

This call will create a new comment on behalf of the user and attach it to the story specified. It returns
the comment that was just created, or an error code.

 Definition

    POST /api/v1/stories/:id/reply

 Example Request

```shell
$ curl -X POST \
  -d 'comment[body]=Kicking off the conversation.' \
  -H 'Authorization: Bearer <your access token>' \
  'https://api-news.layervault.com/api/v1/stories/36524/reply'
```

 Example Response

```json
{
  "comment": {
    "body": "Kicking off the conversation.",
    "comments": [],
    "created_at": "2014-01-24T16:53:08Z",
    "depth": 0,
    "id": 9000,
    "vote_count": 0,
    "url": "https://news.layervault.com/comments/9000",
    "user_display_name": "Kelly S.",
    "user_id": 1
  }
}
```

#### Searching for Stories

This call will [search through Designer News](https://news.layervault.com/search) stories and return any matching
stories. Searches are specified with a `query` parameter

 Definition

    GET /api/v1/stories/search

 Example Request

```shell
$ curl 'https://api-news.layervault.com/api/v1/stories/search?query=Kelly%20Sutton&client_id=abc123'
```

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
      "title": "Kelly Sutton is pretty cool, I guess.",
      "url": "http://localhost:3000/click/stories/13627",
      "vote_count": 11,
      "sponsored": false
    },
    ...
  ]
}
```
