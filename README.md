# payrobot - Kotlin client library for Payrobot

## Requires

* Kotlin 1.3.41
* Gradle 4.9

## Build

First, create the gradle wrapper script:

```
gradle wrapper
```

Then, run:

```
./gradlew check assemble
```

This runs all tests and packages the library.

## Features/Implementation Notes

* Supports JSON inputs/outputs, File inputs, and Form inputs.
* Supports collection formats for query parameters: csv, tsv, ssv, pipes.
* Some Kotlin and Java types are fully qualified to avoid conflicts with types defined in OpenAPI definitions.
* Implementation of ApiClient is intended to reduce method counts, specifically to benefit Android targets.

<a name="documentation-for-api-endpoints"></a>
## Documentation for API Endpoints

All URIs are relative to *https://api.payrobot.io*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*PaymentApi* | [**createPayment**](docs/PaymentApi.md#createpayment) | **POST** /{currency}/payments | Generate a new one-use address to receive a payment
*PaymentApi* | [**getPayment**](docs/PaymentApi.md#getpayment) | **GET** /{currency}/payments/{paymentId} | Get detailed information about a payment
*WalletApi* | [**createWallet**](docs/WalletApi.md#createwallet) | **POST** /{currency}/wallets | Create new wallet
*WalletApi* | [**createWalletSendRequest**](docs/WalletApi.md#createwalletsendrequest) | **POST** /{currency}/wallets/{walletId}/send-requests | Send funds from a wallet
*WalletApi* | [**getWallet**](docs/WalletApi.md#getwallet) | **GET** /{currency}/wallets/{walletId} | Get Wallet information
*WalletApi* | [**getWalletHistory**](docs/WalletApi.md#getwallethistory) | **GET** /{currency}/wallets/{walletId}/history | Get last transactions of wallet
*WalletApi* | [**getWalletSendRequest**](docs/WalletApi.md#getwalletsendrequest) | **GET** /{currency}/wallets/{walletId}/send-requests/{requestId} | Obtain information of a send request


<a name="documentation-for-models"></a>
## Documentation for Models

 - [payrobot.models.AddressDetail](docs/AddressDetail.md)
 - [payrobot.models.CryptoCurrency](docs/CryptoCurrency.md)
 - [payrobot.models.ErrorResponse](docs/ErrorResponse.md)
 - [payrobot.models.PaymentRequest](docs/PaymentRequest.md)
 - [payrobot.models.Wallet](docs/Wallet.md)
 - [payrobot.models.WalletCreationInfo](docs/WalletCreationInfo.md)
 - [payrobot.models.WalletHistory](docs/WalletHistory.md)
 - [payrobot.models.WalletSendRequest](docs/WalletSendRequest.md)
 - [payrobot.models.WalletTransaction](docs/WalletTransaction.md)


<a name="documentation-for-authorization"></a>
## Documentation for Authorization

All endpoints do not require authorization.
