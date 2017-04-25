Harvest uses Basic Auth over HTTPS for authentication. The username is your Greenhouse API token and the password should be blank. Unauthenticated requests will return an HTTP 401 response.

### Authorization header

Most HTTP clients will automatically use a given username and password to generate the required Authorization header. However, you may need to explicity set this header. The header has the following format:

`Authorization: Basic <base64("username:password")>`

Since only a username needs to be provided in our case, you’ll need to append a `:` (colon) to your Greenhouse API token and then Base64 encode the resulting string.

> **Important**: Use HTTPS for all requests. Requests made over HTTP will always return an HTTP 403 response. Keep your API key a secret!

### Setting credentials with cURL

If you’re making test API requests with cURL you can use the -u flag to set the username and password (which is blank). cURL will automatically generate the Authorization header.

### Setting permissions for API Keys

You can specify which API endpoints your API keys have access to from the Greenhouse Dev Center. This will allow you to permit or deny access to each endpoint individually. Any API keys created before January 18th, 2017 will have full permissions to all API endpoints that existed at that time, but any new API keys created after that point will need to be explicitly granted any required endpoint permissions.

To add or remove endpoint permissions on an API key, go to the Dev Center in Greenhouse, click “API Credential Management,” then click “Manage Permissions” next to your Harvest API Key. From there, check or uncheck permissions for any endpoints.
