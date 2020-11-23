
# WalletTransaction

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**amount** | **kotlin.String** | Amount of the transaction:   * &#x60;Negative number (&lt; 0)&#x60; is a withdrawal   * &#x60;Positive number (&gt; 0)&#x60; is a deposit  |  [optional]
**addresses** | [**kotlin.Array&lt;AddressDetail&gt;**](AddressDetail.md) | Address(es) involved:   * &#x60;payments&#x60; address(es) where payment was received   * &#x60;withdrawals&#x60; address(es) where funds were sent  |  [optional]
**timestamp** | **kotlin.Int** | Timestamp of the transaction expressed in &#x60;Unix Timestamp&#x60; |  [optional]



