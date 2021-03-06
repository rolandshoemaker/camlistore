# Application Environment

Camlistore applications run with the following environment variables set:

`CAMLI_API_HOST` (string)
: URL prefix of the Camlistore server which the app should use to make API calls.
  It always ends in a trailing slash. Examples:
   -   https://foo.org:3178/pub/
   -   https://foo.org/pub/
   -   http://192.168.0.1/
   -   http://192.168.0.1:1234/

`CAMLI_APP_BACKEND_URL` (string)
: URL of the application's process, always ending in a trailing slash. That path
  represents the top-most path that requests will hit. The path usually matches
  the path as visible in the outside world when camlistored is proxying an app,
  but that is not guaranteed. Examples:
   -  https://foo.org:3178/pub/
   -  https://foo.org/pub/
   -  http://192.168.0.1/
   -  http://192.168.0.1:1234/

`CAMLI_APP_CONFIG_URL` (string)
: URL containing JSON configuration for the app. The app should once, upon
  startup, fetch this URL (using CAMLI_AUTH) to retrieve its configuration data.
  The response JSON is the contents of the app's "appConfig" part of the config
  file.

`CAMLI_AUTH` (string)
: Username and password (username:password) that the app should use to
  authenticate over HTTP basic auth with the Camlistore server. Basic auth is
  unencrypted, hence it should only be used with HTTPS or in a secure (local
  loopback) environment.
