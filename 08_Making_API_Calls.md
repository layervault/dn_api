## Making API Calls

Once you have your access token, making some API calls from the command line is also easy. For authenticated requests, which require an Authorization header:

```shell
curl -H 'Authorization: Bearer <your access token>' \
  'https://api-news.layervault.com/api/v1/me'
```

For unauthenticated requests, the Designer News API is setup with Cross-Origin Resource Sharing (CORS) rules that allow you to access it from any domain without using something like JSONP.
