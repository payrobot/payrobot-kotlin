# PaymentApi

All URIs are relative to *https://api.payrobot.io*

Method | HTTP request | Description
------------- | ------------- | -------------
[**createPayment**](PaymentApi.md#createPayment) | **POST** /{currency}/payments | Generate a new one-use address to receive a payment
[**getPayment**](PaymentApi.md#getPayment) | **GET** /{currency}/payments/{paymentId} | Get detailed information about a payment


<a name="createPayment"></a>
# **createPayment**
> PaymentRequest createPayment(currency, type, destination, amount, paramCallback, reference)

Generates a new one-use address to receive a payment. It callbacks your
web/app server as soon as it's paid and confirmed.


**Payment can be `forwarded` to another address or it can be `stored` in
a payrobot.io wallet**


---

## Important

  * Unpaid requests are deleted after **3 hours** of theirs creation
  * Confirmed payments information is deleted after **3 days** of being confirmed

---

## Minimum Amounts


  * `Bitcoin`: 0.0001 BTC
  * `Litecoin`: 0.001 LTC
  * `Bitcoin Cash`: 0.001 BCH

---

## Callbacks

A **payment notificacion** will be sent to your callback url in the
following scenarios:

  1. *Payment is received partially*
  2. *Payment is being confirmed by network*
  3. *Payment is confirmed at least with 1 confirmation*


The callback sent to your callback url is a **POST** request with the
following parameters:


*Example:*

    currency:         "BTC"
    paymentId:        "698fd3f6-5482-4798-8a46-6732af440616"
    address:          "3KoUDMfrov91G4SXaCKGvTWDjGia9Jod5b"
    type:             0
    partialAmount:    "0.00"
                      //Partial amount received when payment is incomplete
    remainingAmount:  "0.00"
                      //Remaining amount to pay when payment is incomplete
    amount:           "0.1"
    feePct:           0.90
    feeAmount:        "0.0009"
    finalAmount:      "0.0991"
    destination:      "698fd3f6-5482-4798-8a46-6732af440616"
    reference:        "12345"
    status:           2

### Example
```kotlin
// Import classes:
//import payrobot.infrastructure.*
//import payrobot.models.*

val apiInstance = PaymentApi()
val currency : kotlin.String = btc // kotlin.String | Object Currency:   * `btc`: Bitcoin   * `ltc`: Litecoin   * `bch`: Bitcoin Cash 
val type : kotlin.Int = 0 // kotlin.Int | * `0: Receive and forward` payment is forwarded to a desired coin address once it's confirmed  * `1: Receive and store` payment is stored in a payrobot.io wallet 
val destination : kotlin.String = bc1qzlza4ke65fa2sqacjfu5vtwy8ar6x8xttgk999 // kotlin.String | * For `Receive and forward` payment is the `ADDRESS` where the payment is going to be forwarded as soon as it's confirmed. **ADDRESS HAS TO BE OF THE SAME TYPE OF CURRENCY**  * For `Receive and store` payment is the payrobot.io `WALLET ID` where the payment is going to be stored as soon as it's confirmed. **WALLET HAS TO BE OF THE SAME TYPE OF CURRENCY** 
val amount : java.math.BigDecimal = 0.0129 // java.math.BigDecimal | Amount of the payment
val paramCallback : kotlin.String = https://your-callback-url.com // kotlin.String | Your URL where payrobot.io will send the status of the payment (Webhook)
val reference : kotlin.String = Bill123 // kotlin.String | Optional custom reference to identify the payment
try {
    val result : PaymentRequest = apiInstance.createPayment(currency, type, destination, amount, paramCallback, reference)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PaymentApi#createPayment")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PaymentApi#createPayment")
    e.printStackTrace()
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **currency** | **kotlin.String**| Object Currency:   * &#x60;btc&#x60;: Bitcoin   * &#x60;ltc&#x60;: Litecoin   * &#x60;bch&#x60;: Bitcoin Cash  | [enum: btc, ltc, bch]
 **type** | **kotlin.Int**| * &#x60;0: Receive and forward&#x60; payment is forwarded to a desired coin address once it&#39;s confirmed  * &#x60;1: Receive and store&#x60; payment is stored in a payrobot.io wallet  | [enum: 0, 1]
 **destination** | **kotlin.String**| * For &#x60;Receive and forward&#x60; payment is the &#x60;ADDRESS&#x60; where the payment is going to be forwarded as soon as it&#39;s confirmed. **ADDRESS HAS TO BE OF THE SAME TYPE OF CURRENCY**  * For &#x60;Receive and store&#x60; payment is the payrobot.io &#x60;WALLET ID&#x60; where the payment is going to be stored as soon as it&#39;s confirmed. **WALLET HAS TO BE OF THE SAME TYPE OF CURRENCY**  |
 **amount** | **java.math.BigDecimal**| Amount of the payment |
 **paramCallback** | **kotlin.String**| Your URL where payrobot.io will send the status of the payment (Webhook) |
 **reference** | **kotlin.String**| Optional custom reference to identify the payment | [optional]

### Return type

[**PaymentRequest**](PaymentRequest.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

<a name="getPayment"></a>
# **getPayment**
> PaymentRequest getPayment(currency, paymentId)

Get detailed information about a payment

Gets detailed information about a payment

### Example
```kotlin
// Import classes:
//import payrobot.infrastructure.*
//import payrobot.models.*

val apiInstance = PaymentApi()
val currency : kotlin.String = btc // kotlin.String | Object Currency:   * `btc`: Bitcoin   * `ltc`: Litecoin   * `bch`: Bitcoin Cash 
val paymentId : kotlin.String = 698fd3f6-5482-4798-8a46-6732af440616 // kotlin.String | Payment ID to query
try {
    val result : PaymentRequest = apiInstance.getPayment(currency, paymentId)
    println(result)
} catch (e: ClientException) {
    println("4xx response calling PaymentApi#getPayment")
    e.printStackTrace()
} catch (e: ServerException) {
    println("5xx response calling PaymentApi#getPayment")
    e.printStackTrace()
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **currency** | **kotlin.String**| Object Currency:   * &#x60;btc&#x60;: Bitcoin   * &#x60;ltc&#x60;: Litecoin   * &#x60;bch&#x60;: Bitcoin Cash  | [enum: btc, ltc, bch]
 **paymentId** | **kotlin.String**| Payment ID to query |

### Return type

[**PaymentRequest**](PaymentRequest.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

