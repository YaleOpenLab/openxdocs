# Investors

{% api-method method="post" host="https://api.openx.solar" path="/investor/register" %}
{% api-method-summary %}
Register Investor
{% endapi-method-summary %}

{% api-method-description %}
curl -X POST -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" -d 'username=vg&pwhash=e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716&name=varunram&seedpwd=x&token=XEtmufgCPuKZGZkOUDUUEMBIqbuLIAwJ' "http://api2.openx.solar/investor/register"
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="seedpwd" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```text
{
    "U": {
        "Index": 325,
        "Name": "",
        "Description": "",
        "Image": "",
        "FirstSignedUp": "Tuesday, 31-Mar-20 09:23:16 UTC",
        "Address": "",
        "City": "",
        "ZipCode": "",
        "Country": "",
        "RecoveryPhone": "",
        "Email": "varunram",
        "Notification": false,
        "StellarWallet": {
            "PublicKey": "GB4JNGNMUSXPAMR46DGGTT5N2C6BJJ2PBSWGZNPQAQRAOSHUMF7IIXKO",
            "EncryptedSeed": "bdAeWLgKEgxchw9694SxbjZG3ZC08MvnSGtEu5ep4yAsgPzhz6jNzMxsoU+MQGbvTff4BBktGSIld4aaEdo0BQpnPCZv4hMj",
            "SeedPwhash": ""
        },
        "AlgorandWallet": {
            "WalletName": "",
            "WalletID": ""
        },
        "Username": "vg",
        "Pwhash": "d9290081d361d9323a99180a8a543b82a85517fdb790d41e66956da84bb2de0d287daa3b11a624cdda5f58f2b39da317b671f2142e390e4b2cb3a75eed8eb3e0",
        "Kyc": false,
        "Admin": false,
        "Inspector": false,
        "Banned": false,
        "Reputation": 0,
        "LocalAssets": null,
        "RecoveryShares": ["rSkd0PPoljFJDhpVcdXA1NOFFvTMr4mo9Imc5rGq0c4=oCRQMb5NU2Ajp6D_dtlgadXjbSDfwyntcTw2bK_PuYo=ai0AuOg8HLFjrGKqJ3M_CEb7QNEDRLMI317r2MjTP4c=g0iop9V4r79DGoll_yRvk8UlLRa1ZxhX-qirE2SaHLI=", "mjKjKUVSh8vrjsoG_adD8dyZ0dsGDcofj3jID-tLjO4=1OEQRbZvtIkOVGijLr7h8X74XTjb3qzFaIa4uETgRTk=PRcSWv8g6jCINgYneQ7GjKdofDhrQRMlwriLc-kY_YE=oblSn3oW6dgNeHOoDNMeiFlxLb_MeEwxRYcYIsw8HVg=", "8QtD6LVYsaXl1_bb021RUhoj3rkIKMIjBMrnJ3BTo-A=3FYEQ6ArLjAnZ6yfmgVPKIN7i3LCHhDeRjfewozskg4=SDnyGJL8NU4haVZC7-QkiWihIrir_w66jGQjIrGUDiE=ekDw6vsIxTi-TCI99a2j-yYAXub17Og5I5ilp-W6ZxA="],
        "PwdResetCode": "",
        "SecondaryWallet": {
            "PublicKey": "GCXAJK6HJG4WO6Y6WGRVVN6AAKBF7267RT3EYFQPC7IV4M23ASGM4E3U",
            "EncryptedSeed": "bdcdULgfDww+mQV69PrBEjxOwu2q+c+JRXJEoP7C4jspmOeT2rHGrdht2V2EWwHxNOrqBAg0GS1kEBBP9y7WUh1ucWK5+OwQ",
            "SeedPwhash": ""
        },
        "EthereumWallet": {
            "Address": "0x96654547A297b86A1f761aEB86AAE35D0d7177eE",
            "PublicKey": "da243881752432a4aa09405fa2e8c292e1e6450de9bc60d5fad00b279e62a2a166ea1287a4c26018f8ad9aac8a97e9023e9a960df55b1b5df07ebff6416e063c",
            "PrivateKey": "a9b0804567e930e72719a442faecb8e9c388c8e059260981afb9fa37491bfc4c"
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
            "Url": "",
            "AccountId": ""
        },
        "AccessToken": "",
        "AccessTokenTimeout": 0,
        "Mailbox": null,
        "Legal": false,
        "ProfileProgress": 0
    },
    "C": {
        "CompanyType": "",
        "Name": "",
        "LegalName": "",
        "AdminEmail": "",
        "PhoneNumber": "",
        "Address": "",
        "Country": "",
        "City": "",
        "ZipCode": "",
        "TaxIDNumber": "",
        "Role": ""
    },
    "Company": false,
    "VotingBalance": 0,
    "AmountInvested": -1,
    "InvestedSolarProjects": null,
    "InvestedSolarProjectsIndices": null,
    "SeedInvestedSolarProjects": null,
    "SeedInvestedSolarProjectsIndices": null
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="https://api.openx.solar" path="/investor/validate" %}
{% api-method-summary %}
Validate Investor
{% endapi-method-summary %}

{% api-method-description %}
curl -X GET "https://api2.openx.solar/investor/validate?username=john&token=pmkjMEnyeUpdTyhdHElkBExEKeLIlYft"
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

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

{% api-method method="get" host="https://api.openx.solar" path="/investor/all" %}
{% api-method-summary %}
Get all Investors
{% endapi-method-summary %}

{% api-method-description %}
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "http://api2.openx.solar/investor/all"
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

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

{% api-method method="post" host="https://api.openx.solar" path="/investor/register" %}
{% api-method-summary %}
Invest
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="amount" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="projIndex" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="seedpwd" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

{% api-method method="post" host="https://api.openx.solar" path="/investor/register" %}
{% api-method-summary %}
Vote
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="projIndex" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="votes" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

{% api-method method="post" host="https://api.openx.solar" path="/investor/localasset" %}
{% api-method-summary %}
Create local asset
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="assetName" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

{% api-method method="post" host="https://api.openx.solar" path="/investor/sendlocalasset" %}
{% api-method-summary %}
Send local asset
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="amount" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="destination" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="seedpwd" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="assetName" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

{% api-method method="post" host="https://api.openx.solar" path="/investor/sendemail" %}
{% api-method-summary %}
Send email
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="to" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="message" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

{% api-method method="get" host="https://api.openx.solar" path="/investor/dashboard" %}
{% api-method-summary %}
Investor Dashboard
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

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

{% api-method method="post" host="https://api.openx.solar" path="/investor/company/set" %}
{% api-method-summary %}
Set Company Bool
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

{% api-method method="post" host="https://api.openx.solar" path="/investor/company/details" %}
{% api-method-summary %}
Store company details
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="role" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="zipcode" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="city" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="country" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="address" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="legalname" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="name" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="companytype" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="token" type="string" required=true %}

{% endapi-method-parameter %}

{% api-method-parameter name="username" type="string" required=true %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
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

