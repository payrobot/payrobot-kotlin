
# WalletSendRequest

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**currency** | [**CryptoCurrency**](CryptoCurrency.md) |  |  [optional]
**walletId** | **kotlin.String** | Unique ID of the new created Wallet |  [optional]
**requestId** | **kotlin.String** | ID of this transaction, it can be used letter in the callback or to query it |  [optional]
**timestamp** | **kotlin.Int** | Request creation date expressed in UNIX timestamp |  [optional]
**lastupdate** | **kotlin.Int** | Last update expressed in UNIX timestamp |  [optional]
**amount** | **kotlin.String** | Total amount sent from wallet |  [optional]
**callback** | **kotlin.String** | Optional callback to notify your web / app as soon as the send request has been fully broadcasted to the network |  [optional]
**destination** | [**kotlin.Array&lt;AddressDetail&gt;**](AddressDetail.md) | Array with all the destination coin addres(es) and the amount(s) to send  |  [optional]
**txid** | **kotlin.String** | Tx Hash. *Only available in requests with confirmed status*  |  [optional]
**status** | **kotlin.Int** | Status of this send request:   * &#x60;0: Queued&#x60; Request has been queued for broadcasting. It usually takes few seconds under normal conditions   * &#x60;1: Broadcasted&#x60; Request has been fully broadcasted to Bitcoin Network   |  [optional]
**error** | **kotlin.Boolean** | &#x60;true&#x60; is there was a problem. &#x60;false&#x60; if not  |  [optional]



