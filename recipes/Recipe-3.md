# Recipe #1

ATM Transaction Enrichment 

---
- [Step 1: Create Keys](#step-1-create-keys)
- [Step 2: Get Enrichment Details](#step-2-get-payment-details)



---

## Step 1: Create Keys
Please connect with implementation team to enroll 


## Step 2: Get enrichment details
The ATM Based enrichment

```json
{
   "transactionDescription": "ATM CASH DEPOSIT ON 03/07 4580 Jimmy Lee Smith Pkwy Hiram GA 0001648 ATM ID 0723N CARD 4487"
}
```


<!--
type: tab
titles: Request, Response
-->

##### Example of a ATM transaction request using `transactionDescription`.

```json
{
   "transactionDescription": "ATM CASH DEPOSIT ON 03/07 4580 Jimmy Lee Smith Pkwy Hiram GA 0001648 ATM ID 0723N CARD 4487"
}
```

<!--
type: tab
-->

##### Example of a ATM transaction enrichment response.

<!-- theme: info -->
> See [Response Handling](?path=docs/Resources/Guides/Response-Codes/Response-Handling.md) for more information.

```json
{
    "enrichedStatus": "MERCHANT_AND_STORE_RESOLVED",
    "enrichedMerchantName": "Wells Fargo Bank",
    "mcc": "A039",
    "transactionCategory": "Miscellaneous Income",
    "transactionSubCategory": "Deposit",
    "logoUrl": "https://d25gxhepcf5qi6.cloudfront.net/eaas_qa/logo/5d11cffd-d5da-4aa6-8c6b-590abcf36247.png",
    "ondotMerchantId": "5d11cffd-d5da-4aa6-8c6b-590abcf36247",
    "ondotStoreId": "4b4c7f88-6d4b-4116-a9e0-43c122960718",
    "enrichedMerchantAddress": "4580 Jimmy Lee Smith Pkwy",
    "enrichedMerchantCity": "Hiram",
    "enrichedMerchantState": "GA",
    "enrichedMerchantPostalCode": "30141",
    "enrichedMerchantCountry": "US",
    "enrichedMerchantLatitude": "33.890003",
    "enrichedMerchantLongitude": "-84.75211",
    "enrichedMerchantLocationType": "store",
    "url": "https://www.wellsfargo.com",
    "hours": {
        "sunday": [
            [
                "00:00",
                "23:59"
            ]
        ],
        "saturday": [
            [
                "00:00",
                "23:59"
            ]
        ],
        "tuesday": [
            [
                "00:00",
                "23:59"
            ]
        ],
        "friday": [
            [
                "00:00",
                "23:59"
            ]
        ],
        "thursday": [
            [
                "00:00",
                "23:59"
            ]
        ],
        "wednesday": [
            [
                "00:00",
                "23:59"
            ]
        ],
        "monday": [
            [
                "00:00",
                "23:59"
            ]
        ]
    },
    "transactionType": "cp",
    "accountTransactionType": "atm",
    "enrichedTransactionDescription": "ATM Cash Deposit Wells Fargo Bank",
    "enrichedStandardMerchantDomain": "wellsfargo.com"
}
```

<!-- type: tab-end -->


---
## See also


---
