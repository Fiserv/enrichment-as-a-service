# Recipe #2

## Account Transaction Enrichment 

<!--
type: tab
titles: Request, Response
-->

##### Example of a Account transaction request using `transactionDescription`.

```json
{
   "transactionDescription": "BILL PAY CHASE HOME FINANCE RECURRING xxxxxx0312 ON 01-13"
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
    "enrichedMerchantName": "Chase Bank",
    "mcc": "6011",
    "transactionCategory": "Transfers & Adjustments",
    "transactionSubCategory": "Other Transfers & Adjustments",
    "logoUrl": "https://d25gxhepcf5qi6.cloudfront.net/eaas_qa/logo/9844ed5c-0609-42eb-9f6d-bac804f51ea9.png",
    "enrichedMerchantCountry": "US",
    "url": "https://www.chase.com",
    "transactionType": "cnp",
    "accountTransactionType": "billpay",
    "enrichedTransactionDescription": "Chase Home Finance"
}
```

<!-- type: tab-end -->


---
## See also


---
