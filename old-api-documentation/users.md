# Users

### Get Authentication Token

`POST /token` returns an authentication token that is valid for 24 hours

```text
curl -X POST -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" -d 'username=admin&pwhash=e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716' "https://localhost:8081/token"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Validate User

`GET /user/validate` validates a specific user and returns the user struct

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" "http://localhost:8080/recipient/validateusername%3Dadmin%26token%3DIpJoKNsmnceWUZwqMKeAaKytGKgeWocf"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Get All Balances

`GET /user/balances` returns all balances associated with the user's primary stellar account

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" "http://localhost:8080/user/balances?username=admin&token=mpOZmBnheScFstJPRNnXAqKDoYgBkxHs"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Get XLM Balance

`GET /user/balance/xlm` returns the XLM balance belonging to the user's primary stellar account

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" "http://localhost:8080/user/balance/xlm?username=admin&token=mpOZmBnheScFstJPRNnXAqKDoYgBkxHs"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Get Asset Balance

`GET /user/balance/asset` returns the asset balance corresponding to the asset code belonging to the user's primary stellar account

```text
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/balance/asset?username=john&token=mpOZmBnheScFstJPRNnXAqKDoYgBkxHs&asset=STABLEUSD"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| asset | The name of the asset whose balance one wants to query |

### Get ipfs hash

`GET /ipfs/getdata` returns the data associated with a particular ipfs hash

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" "http://localhost:8080/ipfs/getdata?hash=QmcLDXuVVsvXQwiX7QitsUzjyuuY72s2Aa9BWA34eXJyK6&username=admin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| hash | The hash that the user wants to query |

### KYC a user

`GET /user/kyc` sets the passed user's kyc flag to true

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| userIndex | The index of the user whose kyc status is to be set to true |

### Send XLM to another user

`GET /user/sendxlm` sends xlm to another user

```text
  curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/sendxlm?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&seedpwd=x&amount=1&destination=GCHKX52XNXJ4PWG4TJYR7SEHFBBVDJWRGA22ELSISYLMRCDRSBLSL3MH"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seedpwd | The seedpwd of the source account |
| destination | The destination that the caller wishes to send funds to |
| amount | The amount the caller wishes to send |

### View all users without kyc

`GET /user/notkycview` returns all users without kyc

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/notkycview?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### View all users with kyc

`GET /user/kycview` returns all users with kyc

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/kycview?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Get XLM from testnet faucet

`GET /user/askxlm` asks XLM from the Stellar Faucet

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/askxlm?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Trust Asset

`GET /user/trustasset` trusts a specific issuer against a specific asset

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/trustasset?username=martin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&assetCode=STABELUSD&assetIssuer=GCSMRNO2NBLVULZAIAHA7PAPMFXXLFMLMEAZ23XPNGWMNSY2RL6GJYZR&limit=100&seedpwd=x"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seedpwd | The seedpwd of the source account |
| assetCode | The Code of the asset |
| assetIssuer | The issuer of the asset the caller wants to trust |

### Upload File

`POST /upload` uploads a file to ipfs and returns the ipfs hash of the uploaded file

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| file | The file to be uploaded |

### Get platform email

`GET /platformemail` returns the email of a platform

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/platformemail?username=martin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Ping Teller

`GET /tellerping` pings a teller to check if its up

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/tellerping?username=martin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Increase Trust Limit \(Investor\)

`GET /user/increasetrustlimit` increases an investor's stablecoin trust limit

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/increasetrustlimit?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&trust=10&seedpwd=x"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seedpwd | The seedpwd of the source account |
| trust | The amount that the trust has to be increased by |

### Send Recovery Secrets

`GET /user/sendrecovery` sends recovery secrets to the emails specified

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/sendrecovery?username=samuel&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&email1=varunramganesh@gmail.com&email2=varunramganesh@gmail.com&email3=varunramganesh@gmail.com"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| email1 | The email of the first trusted entity |
| email2 | The email of the second trusted entity |
| email3 | The email of the third trusted entity |

### Recover Seed from secrets

`GET /user/seedrecovery` constructs the seed from the recovery secrets passed

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/seedrecovery?username=samuel&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&secret1=Z0Y8ojGOFs1hw_yNjpbI2jARd1VXjxe9Z1ZjWVN5Li0&secret2=gVRQbkIv4bA6MyazZMpx8MzaijiaQuqPwX-yMU8Ztzw"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| secret1 | The secret from any one of the three trusted entities |
| secret2 | The secret from any one of the three trusted entities |

### Generate New Secrets

`GET /user/newsecrets` constructs new recovery secrets

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/newsecrets?username=samuel&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&email1=varunramganesh@gmail.com&email2=varunramganesh@gmail.com&email3=varunramganesh@gmail.com&seedpwd=x"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seedpwd | The seedpwd of the user |
| email1 | The email of the first trusted entity |
| email2 | The email of the second trusted entity |
| email3 | The email of the third trusted entity |

### Reset Password

`GET /user/resetpwd` resets the password of a user

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/resetpwd?email=varunramganesh@gmail.com&seedpwd=x"
```

| Parameter | Description |
| :--- | :--- |
| email | The email id of the user |
| seedpwd | The seed password of the user |

### Set New Password

`GET /user/pwdreset` checks the verification code for a reset password flow and allows a user to reset their password

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/pwdreset?verificationCode=YYfyyffCmWxHjoEt&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&email=varunramganesh@gmail.com&seedpwd=x"
```

| Parameter | Description |
| :--- | :--- |
| email | The email id of the user |
| verificationCode | The verification code sent to the user's email |
| pwhash | The SHA3\(512\) of the user's desired password |
| seedpwd | The seed password of the user |

### Sweep XLM

`GET /user/sweep` sweeps a user's XLM to another address

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/sweep?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&seedpwd=x&destination=GC6NOHUN7FWCBPOLG7KNYUO6VKNJGCO5PQ5ZENG4L6FXIUTJ6VQ3C7NZ"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seedpwd | The seed password of the user |
| destination | The  destination that the user wants to sweep funds to |

### Sweep Asset

`GET /user/sweepasset` sweeps a user's assets to another address

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/sweepasset?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&seedpwd=x&destination=GC6NOHUN7FWCBPOLG7KNYUO6VKNJGCO5PQ5ZENG4L6FXIUTJ6VQ3C7NZ&assetName=STABLEUSD&issuerPubkey=GCSMRNO2NBLVULZAIAHA7PAPMFXXLFMLMEAZ23XPNGWMNSY2RL6GJYZR"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seedpwd | The seed password of the user |
| destination | The  destination that the user wants to sweep funds to |
| issuerPubkey | The issuer of the specific asset the user wants to sweep |
| assetName | The asset that the user wants to sweep |

### Verify KYC

`GET /user/verifykyc` verifies a user's identity

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| selfie | A photo of the user to be used for KYC authentication |

### Give Rating

`GET /user/giverating` gives a feedback rating for a user

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| feedback | The feedback score \(1-5\) that the user wishes to give another user |
| userIndex | The index of the other user |

### Generate 2FA Code

`GET /user/2fa/generate` generates a new two factor authentication secret

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Authenticate 2FA Code

`GET /user/2fa/authenticate` authenticates a passed password with the stored authentication secret

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| password | The password retrieved from the Two Factor Authentication App |

### Change Reputation

`GET /user/reputation` changes a user's reputation

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| reputation | The reputation increase or decrease amount |

### Add Seed

`GET /user/addseed` adds a new seed to the user's account \(replaces existing primary account\)

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| encryptedseed | The encrypted seed of the user |
| seedpwd | The seedpwd that can decrypt the given encrypted seed |
| pubkey | The publickey associated with the seed |

### Add Seed

`GET /user/latestblockhash` gets the latest Stellar blockchain blockhash

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### IPFS Store Data

`GET /ipfs/putdata` stores a given piece of data in ipfs

```text
curl -X POST -H "Content-Type: application/x-www-form-urlencoded" -d 'username=admin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&data=THIS is a CoOl MeSsAgE' "http://localhost:8080/ipfs/putdata"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Add AnchorKYC info

`GET /user/anchorusd/kyc` adds anchorKYC info that can be used to authenticate the user with AnchorUSD.

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| name | The name of the user |
| bdaymonth | The birthday month of the user |
| bdayyear | The name of the user |
| taxcountry | The country of taxation of the user |
| taxid | The tax id of the user |
| addrstreet | The Address\(Street\) of the user |
| addrcity | The Address\(City\) of the user |
| addrpostal | The Address\(Postal\) of the user |
| addrregion | The Address\(Region\) of the user |
| addrcountry | The Address\(Country\) of the user |
| addrphone | The Address\(Phone\) of the user |
| primaryphone | The Primary Phone of the user |
| gender | The Gender of the user |

