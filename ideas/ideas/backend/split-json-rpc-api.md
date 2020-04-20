# Split JSON-RPC API

The JSON-RPC API is in the rpc package of openx/opensolar. To make things easier and in order to add more functions to the API, we should consider splitting it from the main repositories into a pure Javascript based API.

Using Javascript for APIs is standard and comes with many advantages like REST conformance, easy parameter handling, and easy request parsing. Using JS also makes it easier for more developers to work on the API-Frontend integration since both parts will be in JS. JS also has more open source presence, and might help increase contribution traction for the project.

Splitting the API also improves overall modularity of the platform since cross-language part communication would occur within the platform. Security might be improved if this API server is hosted separate from the main openx server.

