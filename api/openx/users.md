# index

{% api-method method="post" host="https://apidocs.openx.solar" path="/token" %}
{% api-method-summary %}
The Get Access Token
{% endapi-method-summary %}

{% api-method-description %}
This endpoint allows you to fetch a token that can be then used to access all endpoints
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="pwhash" type="string" required=true %}
The pwhash of the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Token": "fKQfVnJkYLtSYSRfvVHepADaHVxtJdkX"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://apidocs.openx.solar" path="/validate/user" %}
{% api-method-summary %}
Validate User
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/balances" %}
{% api-method-summary %}
Get User Balances
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
[
  {
    "balance": "10000.0000000",
    "buying_liabilities": "0.0000000",
    "selling_liabilities": "0.0000000",
    "asset_type": "native"
  }
]
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/balances/xlm" %}
{% api-method-summary %}
Get XLM Balance
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
10000
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/balance/asset" %}
{% api-method-summary %}
Get Asset Balance
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="asset" type="string" required=true %}
The name of the asset one wants to query
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
10000
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/ipfs/getdata" %}
{% api-method-summary %}
Get IPFS hash
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="hash" type="string" required=true %}
The ipfs hash whose data you want to retrieve
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
"This is a test string"
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/kyc" %}
{% api-method-summary %}
Set KYC flag to true
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="userIndex" type="string" required=true %}
The index of the user whose kyc status is to be changed
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Code": 200,
  "Status": "OK"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/sendxlm" %}
{% api-method-summary %}
Send XLM to another user
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="amount" type="string" required=true %}
The amount to be transferred
{% endapi-method-parameter %}

{% api-method-parameter name="destination" type="string" required=true %}
The destination Stellar address
{% endapi-method-parameter %}

{% api-method-parameter name="seedpwd" type="string" required=true %}
The password required to unlock the Stellar Wallet of the user
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/notkycview" %}
{% api-method-summary %}
View all users without kyc
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/kycview" %}
{% api-method-summary %}
View all users with kyc
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/askxlm" %}
{% api-method-summary %}
Get XLM from testnet faucet
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/trustasset" %}
{% api-method-summary %}
Trust Asset
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="assetIssuer" type="string" required=true %}
The issuer of the asset
{% endapi-method-parameter %}

{% api-method-parameter name="assetCode" type="string" required=true %}
The asset code
{% endapi-method-parameter %}

{% api-method-parameter name="seedpwd" type="string" required=true %}
The seedpwd of the source account
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="post" host="https://apidocs.openx.solar" path="/upload" %}
{% api-method-summary %}
Upload File
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="file" type="string" required=true %}
The file to be uploaded
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authenticaion token belonging to the user
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/platformemail" %}
{% api-method-summary %}
Get Platform Email
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/tellerping" %}
{% api-method-summary %}
Ping the teller
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/increasetrustlimit" %}
{% api-method-summary %}
Increase Trust Limit
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="trust" type="string" required=true %}
The amount the trust limit has to be increased by
{% endapi-method-parameter %}

{% api-method-parameter name="seedpwd" type="string" required=true %}
The seedpwd of the user
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/sendrecovery" %}
{% api-method-summary %}
Send Recovery Secrets
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="email3" type="string" required=true %}
The email id to send the third secret to
{% endapi-method-parameter %}

{% api-method-parameter name="email2" type="string" required=true %}
The email id to send the second secret to
{% endapi-method-parameter %}

{% api-method-parameter name="email1" type="string" required=true %}
The email id to send the first secret to
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://apidocs.openx.solar" path="/user/seedrecovery" %}
{% api-method-summary %}
Recovery Seed from secrets
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="secret2" type="string" required=true %}
Any one of the three pre-generated secrets
{% endapi-method-parameter %}

{% api-method-parameter name="secret1" type="string" required=true %}
Any one of the three pre-generated secrets
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/newsecrets" %}
{% api-method-summary %}
Generate New Secrets
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="email3" type="string" required=true %}
The email id of the third trusted entity
{% endapi-method-parameter %}

{% api-method-parameter name="email2" type="string" required=true %}
The email id of the second trusted entity
{% endapi-method-parameter %}

{% api-method-parameter name="email1" type="string" required=true %}
The email id of the first trusted entity
{% endapi-method-parameter %}

{% api-method-parameter name="seedpwd" type="string" required=true %}
The seedpwd of the user
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/resetpwd" %}
{% api-method-summary %}
Reset Password
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="seedpwd" type="string" required=true %}
The seedpwd of the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/pwdreset" %}
{% api-method-summary %}
Set New Password
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="seedpwd" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="pwhash" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="verificationCode" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/sweep" %}
{% api-method-summary %}
Sweep XLM
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="destination" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="seedpwd" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/sweepasset" %}
{% api-method-summary %}
Sweep Asset
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="seedpwd" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="assetName" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="issuerPubkey" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="destination" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/verifykyc" %}
{% api-method-summary %}
VerifyKYC
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="selfie" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/giverating" %}
{% api-method-summary %}
Give Rating
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="userIndex" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="feedback" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/2fa/generate" %}
{% api-method-summary %}
Generate 2FA Code
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="userIndex" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="feedback" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/2fa/authenticate" %}
{% api-method-summary %}
Authenticate 2FA Code
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="password" type="string" required=true %}
Password from the 2FA app
{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/reputation" %}
{% api-method-summary %}
Change reputation
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="reputation" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/addseed" %}
{% api-method-summary %}
Add Seed
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="pubkey" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="seedpwd" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="encryptedseed" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/latestblockhash" %}
{% api-method-summary %}
Get Latest Blockhash
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/ipfs/putdata" %}
{% api-method-summary %}
IPFS Store Data
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}



{% api-method method="get" host="https://apidocs.openx.solar" path="/user/anchorusd/kyc" %}
{% api-method-summary %}
Add AnchorKYC Info
{% endapi-method-summary %}

{% api-method-description %}
Validates a specific struct and returns it
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="gender" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="primaryphone" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="addrphone" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="addrcountry" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="addrregion" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="addrpostal" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="addrcity" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="addrstreet" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="taxid" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="taxcountry" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="bdayyear" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="bdaymonth" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}
The username of the user
{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}
The authentication token belonging to the user
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Cake successfully retrieved.
{% endapi-method-response-example-description %}

```text
{
  "Index": 1,
  "Name": "",
  "Description": "",
  "Image": "",
  "FirstSignedUp": "",
  "Address": "",
  "City": "",
  "ZipCode": "",
  "Country": "",
  "RecoveryPhone": "",
  "Email": "",
  "Notification": false,
  "StellarWallet": {
    "PublicKey": "GDKYETBSKSFJ2T2U7JRK6UPPM2BG27MKSV3QSNZHE44M5XJIPOPYZQVK",
    "EncryptedSeed": "bdEEKLEVFxJTnQR/lf61FztX34/E5MD2QHROvJjQ7DNXiviQxdLQrsUdrlidOgOLN+rxGhokHzQJNY8orPZ/f7qYNwKc8j+0",
    "SeedPwhash": ""
  },
  "AlgorandWallet": {
    "WalletName": "",
    "WalletID": ""
  },
  "Username": "admin",
  "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
  "Kyc": false,
  "Admin": true,
  "Inspector": false,
  "Banned": false,
  "Reputation": 0,
  "LocalAssets": null,
  "RecoveryShares": [
    "sCq-Y7CG3TYnDbvlT17hivV7j95V9vCLxqKTsNRAzxI=bAl2aXUtEzEczCvZu5jEvhjim-EkZe5aLL5jZxLpaU4=PEsHHHE765w-sR2K5oLYOOTrwlLQ6AJYpPhMJaZZM-g=-wWv9T3j-8P9kZG9wSI1dFdKiunDI0f9Oyh-nxi4Axs=",
    "UHcgya1dyK3qIbQcKq-w9msdCa3FsazmsvMb7Dy3KYg=7hXJ4_beuRca_dmj3zElH37Scy_5Mhmo0tRaTrPKw9A=GtGVPUcU_d9yEqt4H13Z2KYFem_kWeszTM_OCaUTh3M=qqlbzL61CgZ00KGth8OVN6rQ7IlAnd0EaSYLNkw3VZA=",
    "fBoiKA77wRtu_nuXntFXKkiMHRsujtM2_Rk-JNlWT7g=loa3udbxC4u-eIpiGbwCfJO3vA4f8yV449po8UpjaYs=R_cKraGA8jDyDrzd6gKaQfvq_K9k4l3Nbn2qLtsCVt0=Q5S7tfPnOl1L8tGig2LKysFZ6DvP4UfSzxym31T40fU="
  ],
  "PwdResetCode": "",
  "SecondaryWallet": {
    "PublicKey": "GBKPNRGLJ5EVJGUDGO47SVQ2HD6LSNXEWDJ4NOFVCZFNWNTAGC7Q5HDP",
    "EncryptedSeed": "bdEULLUGBBZPg3tw9+O0cDtfroK6/9XyJGVXv5TZnCYrkveex7Hcut1rp12BXQDwLPfxEBUqBVMTpr4Dor87iFnby5Q0bkMr",
    "SeedPwhash": ""
  },
  "EthereumWallet": {
    "Address": "0xaDC800387a0460f0198A6cd3074f25Bc5633e963",
    "PublicKey": "58f73d50b6cc669dcec126bf7830be5d65453afc9b1804d04a82d57ecda3c8acf74debd9b9255a602e10e875adbc0a19b94bf3950e42a7c8c10690f910505a5e",
    "PrivateKey": "48d363a86fc6d662246d665c35e545a2fba8875e2c91ee779256df6e176e450c"
  },
  "PendingDocuments": null,
  "KYC": {
    "PassportPhoto": "",
    "IDCardPhoto": "",
    "DriversLicense": "",
    "PersonalPhoto": ""
  },
  "StarRating": null,
  "GivenStarRating": null,
  "TwoFASecret": "",
  "AnchorKYC": {
    "Name": "",
    "Birthday": {
      "Month": "",
      "Day": "",
      "Year": ""
    },
    "Tax": {
      "Country": "",
      "Id": ""
    },
    "Address": {
      "Street": "",
      "City": "",
      "Postal": "",
      "Region": "",
      "Country": "",
      "Phone": ""
    },
    "PrimaryPhone": "",
    "Gender": "",
    "DepositIdentifier": "",
    "WithdrawIdentifier": "",
    "AccountId": ""
  },
  "AccessToken": "pmkjMEnyeUpdTyhdHElkBExEKeLIlYft",
  "AccessTokenTimeout": 1579495472,
  "Mailbox": null,
  "Legal": false,
  "ProfileProgress": 0
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

