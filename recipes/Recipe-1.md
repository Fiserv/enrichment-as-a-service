# Recipe #1

## Card Transaction Enrichment 

<!--
type: tab
titles: Request, Response
-->

##### Example of a card transaction request using `transactionDescription`.

```json
{
    "transactionDescription": "PURCHASE AUTHORIZED ON 02/04 COSTCO WHSE #1004 SAN JOSE CA P383036079858356 CARD 1504",
     "mcc": "5411"
}
```

<!--
type: tab
-->

##### Example of a card transaction enrichment response.

<!-- theme: info -->
> See [Response Handling](?path=docs/Resources/Guides/Response-Codes/Response-Handling.md) for more information.

```json
{
    "enrichedStatus": "MERCHANT_AND_STORE_RESOLVED",
    "enrichedMerchantName": "Costco",
    "mcc": "5300",
    "transactionCategory": "Goods & Merchandise",
    "transactionSubCategory": "General Merchandise",
    "logoUrl": "https://d25gxhepcf5qi6.cloudfront.net/eaas_qa/logo/e31b6bec-8fc8-432d-a9f5-fca037e421ad.png",
    "ondotMerchantId": "e2afc3d3-c7e7-4200-b190-dc6fd47dfabc",
    "ondotStoreId": "868db084-6b27-4014-9cdd-a78080e1b851",
    "enrichedMerchantAddress": "1709 Automation Pkwy",
    "enrichedMerchantCity": "San Jose",
    "enrichedMerchantState": "CA",
    "enrichedMerchantPostalCode": "95131",
    "enrichedMerchantCountry": "US",
    "enrichedMerchantLatitude": "37.39066",
    "enrichedMerchantLongitude": "-121.884722",
    "enrichedMerchantLocationType": "store",
    "url": "https://www.costco.com",
    "hours": {
        "sunday": [
            [
                "09:00",
                "19:00"
            ]
        ],
        "saturday": [
            [
                "09:00",
                "19:00"
            ]
        ],
        "tuesday": [
            [
                "09:00",
                "20:30"
            ]
        ],
        "friday": [
            [
                "09:00",
                "20:30"
            ]
        ],
        "thursday": [
            [
                "09:00",
                "20:30"
            ]
        ],
        "wednesday": [
            [
                "09:00",
                "20:30"
            ]
        ],
        "monday": [
            [
                "09:00",
                "20:30"
            ]
        ]
    },
    "transactionType": "cp",
    "accountTransactionType": "card",
    "enrichedTransactionDescription": "Costco Purchase Authorized"
}
```

<!-- type: tab-end -->


---
## See also


---
