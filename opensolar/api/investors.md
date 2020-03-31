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
{
    "U": {
        "Index": 321,
        "Name": "Test Video",
        "Description": "",
        "Image": "",
        "FirstSignedUp": "Thursday, 26-Mar-20 04:11:58 UTC",
        "Address": "Blah",
        "City": "Blah",
        "ZipCode": "222222",
        "Country": "Blah",
        "RecoveryPhone": "",
        "Email": "varunramganesh@gmail.com",
        "Notification": false,
        "StellarWallet": {
            "PublicKey": "GBX7J3XJZAOLXDSX6UXXJF64AAHKAS3ZR4O7FHDAUFQC5CSNYG67KSHD",
            "EncryptedSeed": "bdAQVbMXCmtEhApzluK1bUtDypei6LDtUWVZsI/L8TUukeqUyLDcuNsKqVqDSAzgKJOVFw4pfFEHdsR7BQdPoQAcrNfqlAO7",
            "SeedPwhash": ""
        },
        "AlgorandWallet": {
            "WalletName": "",
            "WalletID": ""
        },
        "Username": "testvid",
        "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
        "Kyc": false,
        "Admin": false,
        "Inspector": false,
        "Banned": false,
        "Reputation": 0,
        "LocalAssets": null,
        "RecoveryShares": [
            "0tfN50L80C36YKoXZouHvswj1wv21kr-Sw4lGHYQkEU=4zrF5C58ucQO_e9U_EkE0OEWjZq-OG3dAbyBKtumvsg=Q43Gz2wF-vKgWiLHnCbrDOhSjBynMLR5RR8K89fmw5E=7Y8yARgCVjrxdyHYAXZCByQ5GnTH7mR8gxQHlWMH1vQ=",
            "S-zFGt3bAUOBkbTv0oaHzF1f1811Al9_BoWR2N_Piw8=lOaRHpYtunHIJ42emdUIs152ulsvoJ_BAqmi4kL62vI=Yq76SfpMHTq-4Q6v8nruWSYspNx8Upr8hN-6kyBiJug=46Yg0OXVi4_pDvK-sQgd_KVPL_tfGy2dDeOsTqkSFaQ=",
            "evTw63X3UH_ldyKMjs5VeVDOqd4pCmiF7t6foJm7TWM=8kUWqJJyEsr5e62L45LPmhEFwSEeTzT32cWqAWj2oDM=gvGwVI39X2Ar-BJoJ6lJ94QvKs6VrPFTP4mp_GGub6c=WGeIZBDrezYSpFxoHz4sYvG5l4NJyQYsA_QHggtNrEo="
        ],
        "PwdResetCode": "",
        "SecondaryWallet": {
            "PublicKey": "GCVN5PEIV43IHOMI5ZNHOLYRESOMUSNT6JHW42B525ESUCA5DG5XZL4Z",
            "EncryptedSeed": "CUjO9I2TlG5Ozesxke+B2Avq5dYcHdfVuFG/ERCdIGA0Oc/mrqqBhm7iLxbSyBV/X4hjoaAI0V0DK8aQtPVAtjEDESzJYxrO",
            "SeedPwhash": ""
        },
        "EthereumWallet": {
            "Address": "0x91cDa7c11dEa71eC607a7226d4fa8f138f0744a4",
            "PublicKey": "4b973c8c57782e34197eb90450f16637dc9ddf0cc7216a306c393cf836fd60ec0206e9672e247f85a106862fb7e6ddb81e56e0511f77371ab21583e27f6678fa",
            "PrivateKey": "db1a8f8cf2daea600625ce2876701aa9bb8a1d0eec75c87461fe6e5051bc797f"
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
            "DepositIdentifier": "336ed6296ff3210bd5ddbf15700a0f5f",
            "WithdrawIdentifier": "01ce541b873e2f9697cfbd1c1b7096ce",
            "Url": "https://sandbox.anchorusd.com/onboarding?account=GBX7J3XJZAOLXDSX6UXXJF64AAHKAS3ZR4O7FHDAUFQC5CSNYG67KSHD&type=withdraw&identifier=01ce541b873e2f9697cfbd1c1b7096ce",
            "AccountId": ""
        },
        "AccessToken": "SRVDaOfeVoEacdYAwOpTPgbqnUrKmnhq",
        "AccessTokenTimeout": 1585647490,
        "Mailbox": null,
        "Legal": false,
        "ProfileProgress": 40
    },
    "C": {
        "CompanyType": "For-Profit",
        "Name": "testvid",
        "LegalName": "Investor Legal",
        "AdminEmail": "varunramganesh@gmail.com",
        "PhoneNumber": "124123",
        "Address": "Blah",
        "Country": "Blah",
        "City": "Blah",
        "ZipCode": "222222",
        "TaxIDNumber": "123123",
        "Role": "ceo"
    },
    "Company": true,
    "VotingBalance": 0,
    "AmountInvested": 200,
    "InvestedSolarProjects": [
        "OXA23d809bb4"
    ],
    "InvestedSolarProjectsIndices": [
        1
    ],
    "SeedInvestedSolarProjects": null,
    "SeedInvestedSolarProjectsIndices": null
}
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
curl -X GET -H "Content-Type: application/x-www-form-urlencoded" -H "Origin: localhost" "https://api2.openx.solar/investor/all?username=admin&token=WORWLPOYeoqnxqQQItIvfGidOGEADrcT"
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
[
    {
        "U": {
            "Index": 1,
            "Name": "Varunram",
            "Description": "",
            "Image": "",
            "FirstSignedUp": "",
            "Address": "",
            "City": "",
            "ZipCode": "",
            "Country": "",
            "RecoveryPhone": "",
            "Email": "varunramganesh@gmail.com",
            "Notification": false,
            "StellarWallet": {
                "PublicKey": "GBAKZUQKORZSN6DYIGHXF5BTPPPMQNGXMYPPIEPAEHF5K72Y3JW62PVO",
                "EncryptedSeed": "bddnWbMeDW9BlRt6loa+cjch35zH5seJJ3davIvQ6yot8/6d2qzJqKENuCmFRGH5I+3zZhswGypaDa/aEjTMuAU+KrfcqbJS",
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
                "DC_WRKYMqZjTG54enO0FaeQvxTVpbSdW8XNFo1efrW8=drxdSFp-IgsXWno-dbObvHz4OF68CdcEdusf4XDtuTc=ESeamHYMyxsYR9t9rdBO_GgtHe4Bx2tbvuMfEIIbMDg=usCCOQg1FQjmeyaDMdWSWSAzE1IV0e1ZAHziCMmZ6YY=",
                "FBoBHvquM1I13QPSV1f0aJyTbkIjhsJ-r-jWm5vGnWY=9oYWkre0t_GOf-EHzYxnu3PgHmiCrMLgO9uzT_Pyf7Y=_C5tNlLjwOCFHOMMkqhJlq9WHTuB9iQXHdG0p0dKeoU=y4RrmuXlhFeT_oX2k7R9Jad9a806wEgH_WMFO2DESis=",
                "oVCAJc7WGTDB2Ydhr__ddve_u3okLx2RxE9ForzSQHk=_WsfxU_m4zykVCPJJx5UWTsmc-rDgnF0C6rzKHTgRX4=dY_11Q1tAbnW7x8zz3Bq2TWyXFlbrj38zAxwcA8_B2o=ENzh8I3sCn5tkST3R499CqEXL6Jo41L9qY13Q70s3Ys="
            ],
            "PwdResetCode": "",
            "SecondaryWallet": {
                "PublicKey": "GDND55FXRAP3PIFQ3KFPA7TZDM23WZLZTOCLOCA4KED6E6Z3ZOH4ZDAR",
                "EncryptedSeed": "bdcfWrMdGxVGhgholfjHFCpDwYjEicrsW25BppXf8jQ38uqS27LSrdVqu1SKQGCLNe/zZws3C1KcpGd366q8PEIYJvGMd1BV",
                "SeedPwhash": ""
            },
            "EthereumWallet": {
                "Address": "0xE13cC33cDEBd62ed8d485d1eC32DaF7D79d3A4B1",
                "PublicKey": "e4e2a1cd524c983b8f2ea849d8017b828a0058a8722d0a0986756f12ebf7bf3152fe6821cbbc666988e76b4a8c3466c99e0da3203f8c92f36bab5bc9779f1b49",
                "PrivateKey": "76893ec5e02cd3a80ecbb267d3eb55f149ad1aa5ba873b9c6d0263c9caf2bf83"
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
            "AccessToken": "WORWLPOYeoqnxqQQItIvfGidOGEADrcT",
            "AccessTokenTimeout": 1585648191,
            "Mailbox": null,
            "Legal": false,
            "ProfileProgress": 0
        },
        "C": {
            "CompanyType": "Social Enterprise",
            "Name": "admin",
            "LegalName": "Varunram Ganesh",
            "AdminEmail": "",
            "PhoneNumber": "",
            "Address": "Admin",
            "Country": "Admin",
            "City": "Admin",
            "ZipCode": "600078",
            "TaxIDNumber": "",
            "Role": "employee"
        },
        "Company": true,
        "VotingBalance": 0,
        "AmountInvested": 0,
        "InvestedSolarProjects": null,
        "InvestedSolarProjectsIndices": null,
        "SeedInvestedSolarProjects": null,
        "SeedInvestedSolarProjectsIndices": null
    },
    {
        "U": {
            "Index": 10,
            "Name": "",
            "Description": "",
            "Image": "",
            "FirstSignedUp": "Tuesday, 04-Feb-20 14:12:55 UTC",
            "Address": "",
            "City": "",
            "ZipCode": "",
            "Country": "",
            "RecoveryPhone": "",
            "Email": "varunramganesh@gmail.com",
            "Notification": false,
            "StellarWallet": {
                "PublicKey": "GCVTFPOFVDQSVOPHV7CCGV2ATC7W4GKKOPTTGERB2QQ36Q3I4GMDWA3P",
                "EncryptedSeed": "bdcSWskBGhFckgFnk/W6FjVcrpaz+sbpSn5co4XO7FVUhOGf2aGws80MpUiOSmHoLuDsDA0uGiAY682wZurd1lQNwYgdpgJJ",
                "SeedPwhash": ""
            },
            "AlgorandWallet": {
                "WalletName": "",
                "WalletID": ""
            },
            "Username": "invafMxw",
            "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
            "Kyc": false,
            "Admin": false,
            "Inspector": false,
            "Banned": false,
            "Reputation": 0,
            "LocalAssets": null,
            "RecoveryShares": [
                "X7orp7CDEDiqHfn7OMgXjlRnWbt3QphugZqPPWm9NzM=4elOrXSlt4IBfk8aHKZWCdWIMb7wKBKOMrEnn5wiFAE=moeHaIjJlxSuJibW9NrK3dI6vJDHCYej_mNE4cW_9-8=EhASDAezBPv8IMyikXI8REfLwmr0nOw3wwvXilbJ0w4=",
                "OCcS6caCGlpM-KGs0W7F_1tpkE2vTeE3mLhXcZZKS5o=m8ApLPli_eMVzJ-dDivVv3QCC2YzzpOsQIcYmh2tJis=RPuusUIg3mp7J4iaLXBumN6hkzWZV2FaAY57rA5dnZM=2kvt2qk1cbdO0CbRFUqm7OdYI19ZnU8uBU-6qllA0x4=",
                "CuyT7aOpVogzWpdmYX209VLlt5E1UFZz0wmuDXxpkFQ=aDNh-xZwG1tvq1xupejj-jxw2oXj7RszN247LiJOJ4o=XlCZoW8HjDyN2G1TysxT5w-Tv7iFxNWbiGfSe0NSiZs=-Xirlt5UuUbKJI5bcnVBz3xklwutBI8co7bZqc5ZAjM="
            ],
            "PwdResetCode": "",
            "SecondaryWallet": {
                "PublicKey": "GDL3NJYVARFUAQBANTTNKY4GK4QXWEE26BENTGQVO2WXSZKU6SYDYA3U",
                "EncryptedSeed": "bdJhSKkJBRU8ghV08v63czBf1p6ljtKMWmxPvv/K7yAyjPqR0bHDr6Zt3F6TTRjiPfXuHn4gfC1n10HGukEC41Tmnrjq1BPm",
                "SeedPwhash": ""
            },
            "EthereumWallet": {
                "Address": "0xFf6EA03eF1CD4E16c89128C9c385C40c506E7837",
                "PublicKey": "1c6d10ed02d814a0031774788fd14c53919fd29b236fffb16adb4e4d735cd5d5398776325e450c89d89becdb9434e49e1c5fc6c9dbf3ec7066c4d194519d2750",
                "PrivateKey": "bd0f8e4a89dcc651db418ba085d0b96b4895d32b8db09636b45202a28adc0a93"
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
    },
    {
        "U": {
            "Index": 100,
            "Name": "Torniketest",
            "Description": "",
            "Image": "",
            "FirstSignedUp": "Thursday, 13-Feb-20 08:41:33 UTC",
            "Address": "",
            "City": "",
            "ZipCode": "",
            "Country": "",
            "RecoveryPhone": "",
            "Email": "varunramganesh@gmail.com",
            "Notification": false,
            "StellarWallet": {
                "PublicKey": "GAXPDSBHS27SHAOEB6UPM3O3VAOXTROW4XFD6ZK2UJQ37GSVQDXJBBNJ",
                "EncryptedSeed": "bdAGVrkJD2s5mwJkj4SrFipArpGo7M6MIxJTtoDI4jQimeKC36nSydkaoi6CSBr7K+3jD3o4Gj+/kjdPujZAmq8L4ZQ3U6V4",
                "SeedPwhash": ""
            },
            "AlgorandWallet": {
                "WalletName": "",
                "WalletID": ""
            },
            "Username": "mitdciyDIPq",
            "Pwhash": "e9a75486736a550af4fea861e2378305c4a555a05094dee1dca2f68afea49cc3a50e8de6ea131ea521311f4d6fb054a146e8282f8e35ff2e6368c1a62e909716",
            "Kyc": false,
            "Admin": false,
            "Inspector": false,
            "Banned": false,
            "Reputation": 0,
            "LocalAssets": null,
            "RecoveryShares": [
                "Cqa-hEYJ6oi7gX62jaiJhManAC-zu_VkiKkIWMNVvBA=eqhYBTPxCRILt4Bx7G-dIDOnbczFfpfVsjFxC93EYh0=VUaHbpGR4qofe26SWz-S4D_MkHNz7bMDjJDmpo4N6FY=HJJ-iUv9MMtRRHXViei-Pf-sHAkcUNvN3oBnOgiRz2E=",
                "ZGgO2anZi8cBU37wIsRiKm4ZMOU4HT2UNhn87ueiZ-8=iN85EEuZDRcuQvbuZRUUmyIzPgbWySFjlfL8vTn6U0s=2Uk0qJuH1iSh_VFAtb0Zz40KUm3yP7MeNf5TCHIjqlE=GJ9-YEn7CB7neVFkrUun7sf0D_IQlK_EtZ8gSndPdIU=",
                "I1jIXx7kTq8uB7zxUgY093Utc-iFc-GjDSyHtZFHi4M=JkRS13XNKcoqbwU23k6cnncHu7OhcMWtc1D78uKw0q0=q3TQF8Tw2UNSiyqbqVtjtEZvVecqwA6nxkENPnFDljY=DiVxHK-fLB2_-RqL00luDoEhCg1COaRum5T1flHx4FI="
            ],
            "PwdResetCode": "",
            "SecondaryWallet": {
                "PublicKey": "GBZGZ6JB47OG2SBBEBUWMS426NW4HSIVCMMM3MIDCS3333FKCM7JO7HI",
                "EncryptedSeed": "bdIAUbUKahtenABnl+C5bTVcyJSj97eIQhRdtJrQ+S0lkOHkzKO2zcIQvy6SX2P3L5CUB3ozAFKHcN0IsdZZPW11h5U3IjoM",
                "SeedPwhash": ""
            },
            "EthereumWallet": {
                "Address": "0xE238CAACd0E6f0C2cB9828C7c9dc654FDF3EA087",
                "PublicKey": "ebcfa99356ddf4e07003a9605b82ddd12ef4c40f673cfa837ebd424a9e4fbc78763f2a265d329922f6b7ad8e9dbb56dfcca020f45c520ef03bb315b56e9dc072",
                "PrivateKey": "803df8fa470ff951af3e9c83db31e2f6cb6bbb40a5aa8d168717c92bf0f930dd"
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
            "AccessToken": "MZZfnCoDybxfPUffFRAVMGVMHlBcPlah",
            "AccessTokenTimeout": 1581585654,
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
        "InvestedSolarProjectsIndices": [
            1
        ],
        "SeedInvestedSolarProjects": null,
        "SeedInvestedSolarProjectsIndices": null
    }
]
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

{% api-method method="post" host="https://api.openx.solar" path="/investor/vote" %}
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
{
    "Your Profile": {
        "Name": "Test Video",
        "Roles": "Investor, Recipient, Entity"
    },
    "Your Investments": {
        "Total Investments": 200,
        "Projects Invested": 1
    },
    "Your Returns": {
        "Net Returns": "$0",
        "RECs Received": "10 MWh"
    },
    "Energy You Facilitate": {
        "My Direct Contributions": "1000 KWh",
        "Total Contributions": "1000 KWh"
    },
    "Main Wallet": "GBX7J3XJZAOLXDSX6UXXJF64AAHKAS3ZR4O7FHDAUFQC5CSNYG67KSHD",
    "Secondary Wallet": "GCVN5PEIV43IHOMI5ZNHOLYRESOMUSNT6JHW42B525ESUCA5DG5XZL4Z",
    "Account Balance 1": 10000203.35964901,
    "Account Balance 2": 403.3999890089035,
    "Balance": 10000606.759638019,
    "Your Invested Projects": [
        {
            "Index": 1,
            "Image": "https://i.ibb.co/8cqdT6n/Asset-3-4x.png",
            "StageDescription": "4 | Finance and Capitalization",
            "Project Name": "5kW Solar at FabIDEAS Coop - Pilot 1",
            "Location": "Aibonito, Puerto Rico, USA",
            "Capacity": "2.5kW",
            "Your Investment": 0,
            "Your Return": "Donation",
            "Investment Rating": "N/A",
            "Impact Rating": "4/4",
            "Project Actions": "No immediate action"
        }
    ]
}
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

