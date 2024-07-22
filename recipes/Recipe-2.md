# Recipe #1

## Account Transaction Enrichment 


## Get Account Transaction enrichment details
The Account Based enrichment

```json
{
   "transactionDescription": "BILL PAY CHASE HOME FINANCE RECURRING xxxxxx0312 ON 01-13"
}
```


<!--
type: tab
titles: Request, Response
-->

##### Example of a Account transaction request using `transactionDescription`.

```json
{
    "enrichedStatus": "MERCHANT_RESOLVED",
    "enrichedMerchantName": "Chase Bank",
    "mcc": "6011",
    "transactionCategory": "Transfers & Adjustments",
    "transactionSubCategory": "Other Transfers & Adjustments",
    "logoUrl": "https://d25gxhepcf5qi6.cloudfront.net/eaas_qa/logo/9844ed5c-0609-42eb-9f6d-bac804f51ea9.png",
    "ondotMerchantId": "0e48f1fe-8a94-44b1-82d2-c0927ad05208",
    "enrichedMerchantCountry": "US",
    "url": "https://www.chase.com",
    "transactionType": "cnp",
    "accountTransactionType": "billpay",
    "enrichedTransactionDescription": "Chase Home Finance"
}
```

<!--
type: tab
-->

##### Example of a Account transaction enrichment response.

<!-- theme: info -->
> See [Response Handling](?path=docs/Resources/Guides/Response-Codes/Response-Handling.md) for more information.

```json
{
    "enrichedStatus": "MERCHANT_RESOLVED",
    "enrichedMerchantName": "Target",
    "mcc": "5411",
    "transactionCategory": "Goods & Merchandise",
    "transactionSubCategory": "Groceries",
    "logoUrl": "https://d25gxhepcf5qi6.cloudfront.net/eaas_qa/logo/44e35331-4778-41fc-85c1-79c35f35995e.png",
    "ondotMerchantId": "44e35331-4778-41fc-85c1-79c35f35995e",
    "enrichedMerchantCity": "Modesto",
    "enrichedMerchantState": "CA",
    "enrichedMerchantCountry": "US",
    "url": "http://www.target.com",
    "transactionType": "cp",
    "accountTransactionType": "card",
    "enrichedTransactionDescription": "Target Purchase Authorized"
}
```

<!-- type: tab-end -->


---
## See also


---
