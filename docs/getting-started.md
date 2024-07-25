<!-- 
type: tab 
titles: Before You Start, Know Our Standard API Structure
-->

# Before You Start
<!-- theme: info -->
> #### Note for Developers 
>
> Before you start the integration, please talk to your Fiserv implementation specialists to obtain the host URLs and API credentials, and follow the API structure to develop your applications.





<a href="#tab-know_our_standard_api_structure" >Next - Know Our Standard API Structure</a> 


<!-- type: tab -->

# Know Our Standard API Structure 

This section describes the standard structure of request and response messages of Integrated Transaction Enrichment RESTful APIs. 

## Request Message

All API requests must contain the following components:

*	[API Method](#api-method)
* [Request URL](#request-url)
*	[Request Header](#request-header)
*	[Request Body](#request-body)
*	[Response Header](#response-header)
*	[Response Message](#response-message)


### API Method

For security reasons, all API methods are set to POST or PUT, irrespective of the operation. 

### Request URL

Request URL is formed by appending Host URL and API path. 

<!-- theme: info -->
> **Request URL = Host URL + API path**
>
>
https://**HOST URL**/transactions/v2/enrichments


The API path along with the method (POST or PUT) is listed under the API Explorer section. 

### Request Header
  
Header parameters are common for all API requests as follows.

|     Header Name      |     Description                                          |     Required      |
|---------------------|----------------------------------------------------------|---------------|
|     ``Authorization`` |    <p>Use your username and password values, appended to the text  as follows: </p> <p> <code> username:password </code></p> <p> **Important:** In Postman, use the **Headers** tab to enter this Authorization header's name and value </p>                      |     Required    |
|     ``deploymentToken`` |    <p>deploymentToken provided by Fiserv Implementation Specialists </p>                      |     Required    |
|     ``Content-Type`` |    <p>application/json </p>                      |     Required    |


**Sample Header Example**
```
"Content-Type":"application/json"
"Authorization":"username:password"
"deploymentToken":"<deploymentToken>"

```

### Request Body

The following example shows the sample payload for **Transaction Enrichment** API request.

```
{
    "transactionDescription": "ATM WITHDRAWAL - SPIRIT OF Alaska 4001 GEIST ROAD FAIRBANKS AKUS",
}
```

### Response Header
  
Header parameters are common for all API responses as follows.

|     Header Name      |     Description                                          |     Required      |
|---------------------|----------------------------------------------------------|---------------|
|     ``traceId`` |    <p>traceId for future reference</p>                      |     Required    |


**Sample Header Example**
```
"traceId":"66a17ce5e2c5c50dcfe8db0bd68c10e2"

```

## Response Message

Upon a successful API request, a response payload will be received with http status code 200. The following is sample response payload.

```
{
    "enrichedStatus": "MERCHANT_AND_STORE_RESOLVED",
    "enrichedMerchantName": "Spirit of Alaska Federal Credit Union",
    "mcc": "6011",
    "transactionCategory": "Transfers & Adjustments",
    "transactionSubCategory": "Other Transfers & Adjustments",
    "logoUrl": "https://d25gxhepcf5qi6.cloudfront.net/eaas_qa/logo/45acebb8-9b4f-49da-a071-9670988dc89b.png",
    "enrichedMerchantAddress": "4001 Geist Rd",
    "enrichedMerchantCity": "Fairbanks",
    "enrichedMerchantState": "AK",
    "enrichedMerchantPostalCode": "99709",
    "enrichedMerchantCountry": "US",
    "enrichedMerchantLatitude": "64.848572",
    "enrichedMerchantLongitude": "-147.822118",
    "enrichedMerchantLocationType": "store",
    "url": "http://www.spiritofak.com",
    "hours": {
        "tuesday": [
            [
                "10:00",
                "18:00"
            ]
        ],
        "friday": [
            [
                "10:00",
                "18:00"
            ]
        ],
        "thursday": [
            [
                "10:00",
                "18:00"
            ]
        ],
        "wednesday": [
            [
                "10:00",
                "18:00"
            ]
        ],
        "monday": [
            [
                "10:00",
                "18:00"
            ]
        ]
    },
    "transactionType": "cp",
    "accountTransactionType": "atm",
    "enrichedTransactionDescription": "ATM Withdrawal Spirit of Alaska Federal Credit Union",
    "enrichedStandardMerchantDomain": "spiritofak.com"
}

```



To view the API documentation, [click here](../api/?type=post&path=/transactions/v2/enrichments).


<!-- type: tab-end -->
