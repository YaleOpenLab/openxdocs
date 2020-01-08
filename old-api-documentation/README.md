---
title: Openx API reference
language_tabs:
  - shell
toc_footers:
  - '<a href=''https://github.com/lord/slate''>Documentation Powered by Slate</a>'
includes:
  - errors
search: true
---

# Old API documentation

## Users

### Authentication Token

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

## Stablecoin

### Get Stablecoin

`GET /stablecoin/get` gets a specific amount of stablecoin exchanging XLM

```text
curl -X
  GET
  "http://localhost:8080/stablecoin/get?seed=SA5DXUTRWHQXOHPISTRLPH55NIUOSV2GB5NDTOSZ7H33KOK2TYYU556O&amount=1&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&username=john"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seed | The seed of the account that requires stablecoin / is willing to exchange xlm for stableusd |
| amount | The amount of xlm that the user wishes to exchange for STABLEUSD |

## Platform

### Get Constants

`GET /platform/getconsts` gets the constants from openx

| Parameter | Description |
| :--- | :--- |
| code | The authentication code of the platform |

### Platform Retrieve User

`GET /platform/user/retrieve` retrieves a user from openx's database

| Parameter | Description |
| :--- | :--- |
| code | The authentication code of the platform |
| key | The index of the user that the platform wants to retrieve |

### Platform User Validate

`GET /platform/user/validate` validates a user with openx's database

| Parameter | Description |
| :--- | :--- |
| code | The authentication code of the platform |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Platform New User

`GET /platform/user/new` creates a new user in openx's database

| Parameter | Description |
| :--- | :--- |
| code | The authentication code of the platform |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seedpwd | The seedpwd of the source account |
| realname | The real name of the user |

### Platform User Validate

`GET /platform/user/collision` checks if a username collides with an existing username

### Retrieve All PLatforms

`GET /platforms/all` retrieves all platforms that are built on openx

## Admin

### Kill Platform

`POST /admin/kill` kills the platform instantly

| Parameter | Description |
| :--- | :--- |
| nuke \(OPTIONAL\) | The nuclear code of the platform |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Freeze Platform

`GET /admin/freeze` freezes the platform instantly

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Generate Nuclear Code

`POST /admin/gennuke` generates a new nuclear code

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Generate Nuclear Code

`GET /admin/platform/all` lists all platforms

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### List all admins

`GET /admin/list` lists all admins

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Generate Nuclear Code

`POST /admin/platform/new` creates a new platform/code paid

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| name | The name of the new platform |
| code | The authentication code of the new platform |
| timeout | The timeout associated with the new platform |

### Send Message

`POST /admin/sendmessage` sends a message directly to the inbox of an openx user

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| subject | The subject of the message |
| message | The message |
| recipient | The recipient of the message |

## Public

### Get Name

```text
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"

  "http://localhost:8080/public/user?index=50"
```

| Parameter | Description |
| :--- | :--- |
| index | The user inex of the user |

### Get All Investors

```text
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"

  "http://localhost:8080/public/investor/all"
```

### Get All Recipients

```text
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"

  "http://localhost:8080/public/recipient/all"
```

### Get Top Reputed Users

```text
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"

  "http://localhost:8080/public/reputation/top"
```

### Get Top Reputed Investors

```text
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"

  "http://localhost:8080/public/investor/reputation/top"
```

### Get Top Reputed Recipients

```text
curl -X
  GET -H "Content-Type: application/x-www-form-urlencoded"
  -H "Origin: localhost"

  "http://localhost:8080/public/recipient/reputation/top"
```

## Investors

### Register Investor

`POST /investor/register` registers a new investor on the opensolar platform

| Parameter | Description |
| :--- | :--- |
| name | The name of the user |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seedpwd | The seed password of the user |
| token | The authentication token belonging to the user |

### Validate Investor

`GET /investor/validate` validates a given investor on the opensolar platform

```text
curl -X GET "http://localhost:8080/investor/validate?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Get All Investors

`GET /investor/all` gets all investors registered on the opensolar platform

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/investor/all"
```

### Invest in a Project

`POST /investor/invest` invests in a project on the opensolar platform

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seedpwd | The seed password of the user |
| projIndex | The project index to invest in |
| amount | The amount to invest |

### Vote towards a project

`POST /investor/vote` votes towards a project

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| votes | The amount of votes to assign towards the project |
| projIndex | The project to vote towards |

### Create local asset

`POST /investor/localasset` creates a local asset

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| assetName | The name of the asset that the investor wants to create |
| seedpwd | The seed password of the user |

### Send local asset

`POST /investor/sendlocalasset` creates a local asset

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| pwhash | The SHA3\(512\) hashed password of the user |
| assetName | The name of the asset that the investor wants to create |
| destination | The destination that the caller wishes to send funds to |
| amount | The amount of the local asset that the user wants to send |

### Send Email to another entity

`POST /investor/sendemail` sends an email to another entity

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| message | The message that the investor wants to convey to the receiver |
| to | The email address of the receiver |

## Recipients

### Get All Recipients

`GET /recipient/all` gets all recipients registered on the opensolar platform

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/recipient/all"
```

### Register Recipient

`POST /recipient/register` registers a recipient on the opensolar platform

| Parameter | Description |
| :--- | :--- |
| name | The name of the user |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seedpwd | The seed password of the user |

### Validate Recipient

`GET /recipient/validate` validates a recipient on the opensolar platform

```text
curl -X GET "http://localhost:8080/recipient/validate?username=martin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Payback

`POST /recipient/payback` pays back the platform on an invested project

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| assetName | The debt asset name owed by the recipient |
| seedpwd | The seed password of the user |
| amount | The amount in stableUS that the user wants to payback |
| projIndex | The index of the project that the recipient wants to payback towards |

### Store Device Id

`POST /recipient/deviceId` stores the deviceId of the teller

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| deviceId | The deviceId \(of the teller\) that the recipient wants to store |

### Store Start time of teller

`POST /recipent/startdevice` stores the start times of the teller

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| start | The start time \(of the teller\) that the recipient wants to store |

### Store location of the teller

`POST /recipient/storelocation` stores the location of the teller

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| location | The location \(of the teller\) that the recipient wants to store |

### Choose blind auction

`GET /recipient/auction/choose/blind` chooses the winning contract by a blind auction

```text
curl -X GET "http://localhost:8080/recipient/auction/choose/blind?username=martin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Choose vickrey auction

`GET /recipient/auction/choose/vickrey` chooses the winning contract by a vickrey auction

```text
curl -X GET "http://localhost:8080/recipient/auction/choose/vickrey?username=martin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Choose time auction

`GET /recipient/auction/choose/time` chooses the winning contract by the least amount of time taken to complete

```text
curl -X GET "http://localhost:8080/recipient/auction/choose/time?username=martin&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |

### Unlock Project

`POST /recipient/unlock/opensolar` unlocks a specific opensoalr project

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| seedpwd | The seed password of the user |
| projIndex | The index of the project needed to unlock |

### Add email address

`POST /recipient/addemail` adds an email address to the recipient's account

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| email | The email address that hte user wishes to add to their profile |

### Finalize project

`POST /recipient/finalize` finalizes a specific project

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| projIndex | The index of the project that has to be finalized |

### Originate project

`POST /recipient/originate` originates a specific project

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| projIndex | The index of the project that has to be finalized |

### Get Trust Limit

`GET /recipient/trustlimit` gets the stablecoin trustlimit of the recipient

```text
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://localhost:8080/user/increasetrustlimit?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&trust=10&seedpwd=x"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| assetName | The asset whose trust limit the user wants to query |

### Store State Hash

`POST /recipient/ssh` stores the state hash of the teller

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| hash | The state hash that the user wishes to store |

### Set one time unlock

`POST /recipient/onetimeunlock` sets the one time unlock password against a recipient's acconut

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| projIndex | The index of the project that has to be finalized |
| seedpwd | The one time password that the recipient wants to store to unlock a specific project |

### Register Teller

`POST /recipient/register/teller` registers a new teller against the recipient's account

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| projIndex | The index of the project that has to be finalized |
| url | The url of the teller associated with the project |

### Get Teller Details

`POST /recipient/teller/details` stores the details of the teller

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| projIndex | The index of the project that has to be finalized |
| url | The url of the teller associated with the project |
| brokerurl | The url of the broker associated with the teller |
| topic | The topic that the teller broadcasts MQTT messages under |

## Projects

### Insert a new project

`POSt /project/insert` inserts a new project into the opensolar platform

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| PanelSize | The size of the panel |
| TotalValue | The total value of the project |
| Location | the location fo the project |
| Metadata | Other metadata associated with the project |
| Stage | The stage at which the project is at |

### Get All Projects

`GET /project/all` gets all projects advertised on the opensolar platform

```text
curl -X GET -H "Origin: localhost" "http://localhost:8080/project/all"
```

This endpoint retrieves the list of all opensolar projects associated with the platform

### Get Specific Project

`GET /project/get` gets a specific project advertised on the opensolar platform

```text
curl -X
  GET -H "Origin: localhost" "http://localhost:8080/project/get?index=1"
```

This endpoint retrieves a specific opensolar project

| Parameter | Description |
| :--- | :--- |
| index | The index of the project that we would like to retrieve |

### Get Projects at a particular stage

`GET /projects` gets projects at a specific stage advertised on the opensolar platform

```text
curl -X GET  "http://localhost:8080/projects?stage=2"
```

| Parameter | Description |
| :--- | :--- |
| stage | The stage at which we would like to see how many projects exist |

### AddHash

`GET /utils/addhash` adds a hash \(contract / other documents\) to be stored on the platform

| Parameter | Description |
| :--- | :--- |
| projIndex | The index of the project |
| choice | The choice \(omh/cch/ipch/rpch/ssh\) that he user wants to store against |
| choicestr | The ipfs hash of the related document |

### Teller Shutdown

`GET /tellershutdown` is an endpoint called when the teller shuts down

| Parameter | Description |
| :--- | :--- |
| projIndex | The index of the project |
| deviceId | The deviceId associated with the teller |
| tx1 | The first half of the state hash stored in the memo field |
| tx2 | The second half of the state hash stored in the memo field |

### Teller Payback

`GET /tellerpayback` is an endpoint called when the teller automatically pays back towards a contract

| Parameter | Description |
| :--- | :--- |
| projIndex | The index of the project |
| deviceId | The deviceId associated with the teller |

## Stages

### Get All Stages

`GET /stages/all` gets all stages that are defined on the opensolar platform

```text
curl -X GET "http://localhost:8080/stages/all"
```

### Get a specific stage

`GET /stages` gets details on a stage defined on the opensolar platform

```text
curl -X GET "http://localhost:8080/stages?index=1"
```

### Promote stages

`GET /stages/promote` advances a project's stage by 1

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| index | The index of the project |

## Particle IO Endpoints

### Get All Devices

```text
curl -X
  GET
"http://localhost:8080/particle/devices?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&productInfo=blah"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| accessToken | The access token of the particle endpoint |
| productInfo | The information associated with the product |

### Get Product Info

```text
curl -X
  GET
  "http://localhost:8080/particle/productinfo?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&productInfo=blah"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| accessToken | The access token of the particle endpoint |
| productInfo | The information associated with the product |

### Ping Device

```text
curl -X
  GET
  "http://localhost:8080/particle/deviceping?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&deviceId=blah"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| accessToken | The access token of the particle endpoint |

### Turn Signal on

```text
curl -X
  GET
  "http://localhost:8080/particle/devicesignal?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&deviceId=blah&signal=on"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| accessToken | The access token of the particle endpoint |
| signal | Boolean value to turn on / off the signal |

### Get Device Id

```text
curl -X
  GET
  "http://localhost:8080/particle/getdeviceid?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&serialNumber=blah"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| pwhash | The SHA3\(512\) hashed password of the user |
| serialNumber | The serial number of the device |

### Get last diagnostic report

```text
curl -X
  GET
  "http://localhost:8080/particle/diag/last?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&deviceId=blah"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| accessToken | The access token of the particle endpoint |
| deviceId | The deviceId of the installed device |

### Get all diagnostic reports

```text
curl -X
  GET
  "http://localhost:8080/particle/diag/all?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah&deviceId=blah"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| accessToken | The access token of the particle endpoint |
| deviceId | The deviceId of the installed device |

### Get user info

```text
curl -X
  GET
  "http://localhost:8080/particle/user/info?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| accessToken | The access token of the particle endpoint |

### Get installed sim card data

```text
curl -X
  GET
  "http://localhost:8080/particle/sims?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft&accessToken=blah"
```

| Parameter | Description |
| :--- | :--- |
| username | The username of the user |
| token | The authentication token belonging to the user |
| accessToken | The access token of the particle endpoint |

## Common

### Ping the platform

```text
curl -X GET  "http://localhost:8080/ping"
```

