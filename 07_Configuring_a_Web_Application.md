### Configuring A Web Application as a LayerVault API client

First of all, make sure that your redirect URI is correctly specified.

Then, when configuring your oAuth 2 client library, tell it to use ```https://api-news.layervault.com/oauth/authorize``` to request authorization and ```https://api-news.layervault.com/oauth/token``` to get access tokens. Most libraries will default to this convention anyway.
