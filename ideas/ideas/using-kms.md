# Using KMS

Currently, the platform seed is encrpyted but the platform seed password is sdtored in the config file used to start openx/opensolar. The platform seed could instead be transferred to a Key Management Service and we can call the platform seed by calling the KMS API.

Using a KMS encrypts storage by default, so we don't have to worry about secrets being  leaked. A KMS also provides high security guarantees and uptime, so the platform seed will not be lost if the server doesnt' work.

A KMS is easy to implement if we move to a docker based architecture since the secrets can be served directly to the container / server instance through AWS IAM roles.

We could also use hardware keys to act as a KMS, and configure the server to use the keys from the hardware device. This improves security since the keys don't reside in a "hot" interface. This however, is better implemented in a self hosted service \(ie a service where openx/solar runs its own hardware\) since configuring hardware keys with AWS or other hosting providers can prove to be tough.

