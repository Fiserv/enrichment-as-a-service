# Recipe #4

## BillPay Transaction Enrichment 

<!--
type: tab
titles: Request, Response
-->

##### Example of a BillPay transaction request using `transactionDescription`.

```json
{
   "transactionDescription": "BILL PAY JODY CHASE MILEAGE UNITED ON-LINE xxxxxxxxxxxx4784 ON 01-09"  
}
```

<!--
type: tab
-->

##### Example of a BillPay transaction enrichment response.

<!-- theme: info -->
> See [Response Handling](?path=docs/Resources/Guides/Response-Codes/Response-Handling.md) for more information.

```json
{
    "enrichedStatus": "MERCHANT_RESOLVED",
    "enrichedMerchantName": "United Airlines",
    "mcc": "A026",
    "transactionCategory": "Transfers & Adjustments",
    "transactionSubCategory": "Bill Payments",
    "logoUrl": "https://d25gxhepcf5qi6.cloudfront.net/eaas_qa/logo/3f3f9a3e-fb58-45b2-bfc4-e7f03b15f72d.png",
    "enrichedMerchantCountry": "US",
    "url": "http://www.united.com",
    "transactionType": "cnp",
    "accountTransactionType": "billpay",
    "enrichedTransactionDescription": "United Airlines Chase"
}
```

<!-- type: tab-end -->


---
## See also


---
