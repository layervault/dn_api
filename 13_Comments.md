### Comments

#### Retrieving Comment Information

This call returns information for a comment.

 Definition

    GET /api/v1/comments/:id

 Example Request

    $ curl -H 'Authorization: Bearer <your access token>' 'https://api.news.layervault.com/api/v1/comments/36524'

 Example Response

```json
{
  "comment": {
    "body": "I would try something other than blue. Purples can be nice depending on how you approach brand design.\r\n\r\nOne often overlooked approach is blank and white. Most companies could benefit from using some shades of grey as the main brand color. You could have accent colours like blue, purple or orange, but mainly back and white.\r\n\r\nThe fun thing about B&W is that it convey simplicity and clarity, without losing its inherited old trust. Definitely worth trying out.\r\n\r\nBut, more than anything I could say, try crazy things. Set aside 20% of the time you dedicate to this project and try other colours: Red, orange, green. You'll be surprised by how testing some crazy ideas can improve your process and, if they don't work in the end, they will sure reflect on your final choice.",
    "comments": [],
    "created_at": "2014-01-24T16:53:08Z",
    "depth": 2,
    "id": 36524,
    "upvotes_count": 0,
    "url": "https://news.layervault.com/comments/36524",
    "user_display_name": "Matt P.",
    "user_id": 4181
  }
}
```

#### Replying to a Comment

This call will create a new comment on behalf of the user and attach it to the comment specified. It returns
the comment that was just created, or an error code.

 Definition

    POST /api/v1/comments/:id/reply

 Example Request

    $ curl -H 'Authorization: Bearer <your access token>' 'https://api.news.layervault.com/api/v1/comments/36524/reply'

 Example Response

```json
{
  "comment": {
    "body": "I agree. Purples are sweet.",
    "comments": [],
    "created_at": "2014-01-24T16:53:08Z",
    "depth": 3,
    "id": 9001,
    "upvotes_count": 0,
    "url": "https://news.layervault.com/comments/9001",
    "user_display_name": "Kelly s.",
    "user_id": 1
  }
}
```

#### Upvoting a Comment

This call will upvote a comment on behalf of the current user. It returns the comment that was upvoted, with an updated `upvotes_count`.

 Definition

    POST /api/v1/comments/:id/upvote

 Example Request

    $ curl -H 'Authorization: Bearer <your access token>' 'https://api.news.layervault.com/api/v1/comments/36524/upvote'

 Example Response

```json
{
  "comment": {
    "body": "I would try something other than blue. Purples can be nice depending on how you approach brand design.\r\n\r\nOne often overlooked approach is blank and white. Most companies could benefit from using some shades of grey as the main brand color. You could have accent colours like blue, purple or orange, but mainly back and white.\r\n\r\nThe fun thing about B&W is that it convey simplicity and clarity, without losing its inherited old trust. Definitely worth trying out.\r\n\r\nBut, more than anything I could say, try crazy things. Set aside 20% of the time you dedicate to this project and try other colours: Red, orange, green. You'll be surprised by how testing some crazy ideas can improve your process and, if they don't work in the end, they will sure reflect on your final choice.",
    "comments": [],
    "created_at": "2014-01-24T16:53:08Z",
    "depth": 2,
    "id": 36524,
    "upvotes_count": 1,
    "url": "https://news.layervault.com/comments/36524",
    "user_display_name": "Matt P.",
    "user_id": 4181
  }
}
```