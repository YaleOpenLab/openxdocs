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
Validate User
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



