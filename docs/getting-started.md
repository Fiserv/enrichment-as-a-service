<!-- 
type: tab 
titles: Before You Start, Know Our Standard API Structure
-->

# Before You Start
<!-- theme: info -->
> #### Note for Developers 
>
> The current user journey enables developers to register for a trial plan that provides access to enrich different kind of transactions. <br><br>To get access to a dedicated test environment, optional and ancillary services, including dedicated technical services, upgrade to a paid Developer Studio subscription plan <a href="https://appmarket.fiservapps.com/fintech" > here</a>.

Before you start the integration, please talk to your Fiserv implementation specialists to obtain the host URLs and API credentials, and follow the API structure to develop your applications.



<a href="#tab-know_our_standard_api_structure" >Next - Know Our Standard API Structure</a> 


<!-- type: tab -->

# Know Our Standard API Structure 

This section describes a standard structure of request and response message of Integrated Transaction Enrichment RESTful APIs. 

## Request Message

All API requests must contain the following components:

*	[API Method](#api-method)
* [Request URL](#request-url)
*	[Request Header](#request-header)
*	[Request Body](#request-body)

For every API request, a response message is obtained that contains a response payload and the status of the API request.

### API Method

For security reasons, all API methods are set to POST or PUT, irrespective of the operation. 

### Request URL

Request URL is formed by appending Host URL and API path. 

<!-- theme: info -->
> **Request URL = Host URL + API path**
>
> https://<URL>/transactions/v2/enrichments


The API path along with the method (POST or PUT) is listed under the API Explorer section of that API on Fiserv Developer Studio. 
Refer the following example to construct a request URL for [**Transaction Enrichment**](../api/?type=post&path=/transactions/v2/enrichments) API:


### Request Header
  
  
Header parameters are common for all API requests of Banking Hub APIs. Header parameters are sent as a JSON object under Integrated Transaction Enrichment header parameter.

|     Header Name      |     Description                                          |     Required      |
|---------------------|----------------------------------------------------------|---------------|
|     ``Authorization`` |    <p>use your username and password values, appended to the text  as follows: </p> <p> <code> username:password </code></p> <p> **Important:** In Postman, use the **Headers** tab to enter Username and Password values </p>                      |     Required    |
|     ``deploymentToken`` |    <p>Deployment Token given while subscriping the enrichment API </p>                      |     Required    |
|     ``Content-Type`` |    <p>application/json </p>                      |     Required    |


**Sample Header Example**
```
"Content-Type":"application/json"
"Authorization":"username:password"
"deploymentToken":"<deploymentToken>"

```

### Request Body

The request body of an API changes based on the type of transaction being processed. Request body contains the detailed information that is required to perform a particular transaction.

**Request Payload** 

The following example shows the sample request payload for **Transaction Enrichment** API request.

```
{
    "transactionDescription": "ATM WITHDRAWAL - SPIRIT OF Alaska 4001 GEIST ROAD FAIRBANKS AKUS",
}
```


## Response Message

Upon a successful API request, a response payload is received. The response payload contains the status and the returned details of the requested API in key-value pairs. The default response format is JSON. 


### Response Payload

The following example shows the sample response payload for **Transaction Enrichment** API request.

```
{
    "enrichedStatus": "MERCHANT_AND_STORE_RESOLVED",
    "enrichedMerchantName": "Spirit of Alaska Federal Credit Union",
    "mcc": "6011",
    "transactionCategory": "Transfers & Adjustments",
    "transactionSubCategory": "Other Transfers & Adjustments",
    "logoUrl": "https://d25gxhepcf5qi6.cloudfront.net/eaas_qa/logo/45acebb8-9b4f-49da-a071-9670988dc89b.png",
    "ondotMerchantId": "45acebb8-9b4f-49da-a071-9670988dc89b",
    "ondotStoreId": "cd458d13-59b6-4f1a-a319-839791c04bd8",
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

To view the API documentation of **Transaction Enrichment** API in API Explorer, [click here](../api/?type=post&path=/transactions/v2/enrichments).


<!-- type: tab-end -->
