
# PaymentRequest

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**currency** | [**CryptoCurrency**](CryptoCurrency.md) |  |  [optional]
**paymentId** | **kotlin.String** | Unique identifier of the payment in selected currency |  [optional]
**address** | **kotlin.String** | One-use address for receive your client payment |  [optional]
**pin** | **kotlin.String** | PIN, it will be required if you need support with this payment.\\ *Note: It&#39;s provided only the first time you create the payment request* |  [optional]
**type** | **kotlin.Int** | * &#x60;0: Receive and forward&#x60; payment is forwarded to a desired coin address once it&#39;s confirmed  * &#x60;1: Receive and store&#x60; payment is stored in a payrobot.io wallet  |  [optional]
**amount** | **kotlin.String** | The payment amount your client has to send to the coin address |  [optional]
**callback** | **kotlin.String** | URL where payrobot.io will send the status of the payment (Webhook) |  [optional]
**feePct** | [**java.math.BigDecimal**](java.math.BigDecimal.md) | Fee percentage that will be discounted |  [optional]
**feeAmount** | **kotlin.String** | Fee amount that will be discounted |  [optional]
**finalAmount** | **kotlin.String** | Final amount of the transaction (Fee discount is already applied)   * For &#x60;Receive and forward&#x60; payment is the total amount to &#x60;forward&#x60; as soon as the payment is confirmed         * For &#x60;Receive and forward&#x60; payment is the total amount to &#x60;store&#x60; in the wallet as soon as the payment is confirmed |  [optional]
**destination** | **kotlin.String** | * For &#x60;Receive and forward&#x60; payment is the coin &#x60;ADDRESS&#x60; where the payment is going to be forwarded as soon as it&#39;s confirmed  * For &#x60;Receive and store&#x60; payment is the &#x60;WALLET ID&#x60; where the payment is going to be stored as soon as it&#39;s confirmed  |  [optional]
**reference** | **kotlin.String** | Custom reference for payment identifying |  [optional]
**timestamp** | **kotlin.Int** | Request creation date expressed in UNIX timestamp |  [optional]
**lastupdate** | **kotlin.Int** | Last update expressed in UNIX timestamp |  [optional]
**status** | **kotlin.Int** | Status of the payment:    * &#x60;0: Idle&#x60; payment has not been paid    * &#x60;1: Incomplete&#x60; payment is being paid partially    * &#x60;2: Confirming&#x60; payment has been received completely but it&#39;s not confirmed by network yet    * &#x60;3: Confirmed&#x60; payment has been paid completely and it has at least &#x60;1&#x60; confirmation by network  |  [optional]
**error** | **kotlin.Boolean** | &#x60;true&#x60; is there was a problem. &#x60;false&#x60; if not  |  [optional]



