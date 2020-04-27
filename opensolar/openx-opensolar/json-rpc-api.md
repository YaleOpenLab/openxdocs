# JSON-RPC API

Opensolar performs all its interactions with the web interface and teller through its JSON-RPC APIs. Some endpoints are public and can be called without a token. Other endpoints are restricted, requiring an account on opensolar and a token.

The token can be fetched by POSTing to `/token` with the username and the 512 byte SHA3 hash of the password. This token is valid for 24 hours but callers can generate a new token even if the timeout interval hasn't been reached.

