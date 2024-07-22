<!-- 
type: tab 
titles: Before You Start, Know Our Standard API Structure, Make Your First API Call
-->

# Before You Start
<!-- theme: info -->
> #### Note for Developers 
>
> The current user journey enables developers to register for a trial plan that provides access to enrich different kind of transactions. <br><br>To get access to a dedicated test environment, optional and ancillary services, including dedicated technical services, upgrade to a paid Developer Studio subscription plan <a href="https://appmarket.fiservapps.com/fintech" > here</a>.

Before you start integration, it is important to register on the Fiserv Developer Studio to test the Enrichment APIs in the Sandbox environment. You may choose to test APIs using the [Third-party API Testing Tools](#tab-make_your_first_api_call) of your choice. However, registration is not required to learn about our APIs and reference documentation.

<!--

[![Video Thumbnail]][Video]  

-->

[![Video Thumbnail]][Video1]  

[Video]: https://user-images.githubusercontent.com/81968767/231950346-2b13475d-f395-4b11-8a55-2d0c93f45813.mp4
[Video Thumbnail]: https://user-images.githubusercontent.com/81968767/232030323-bbde320a-2bf5-4e21-97c0-8fe1a8895913.png

[Video1]: https://github.com/Fiserv/banking-hub/assets/81706748/a776e7c8-bea8-410e-9529-43ca3968327d


## Register on Fiserv Developer Studio
This section describes the process to create an account and workspace on Fiserv Developer Studio to obtain credentials for sandbox testing.

### Creating an Account

Perform the following steps to create an account on Fiserv Developer Studio:
1.	From the top-right corner of the screen, click **Create account**
2.	Populate the required fields and click **Next**
3.	Follow the instructions on the screen to set up your account
4.	Sign in to your Fiserv Developer Studio account once it is activated

### Creating a Integrated Transaction Enrichment Workspace

Workspaces are dedicated spaces for developers to obtain API key, API secret and product related details.

Perform the following steps to create a workspace on Fiserv Developer Studio:

1.	Sign in to your Fiserv Developer Studio account
2.	From the top-right corner of the screen, click **Workspaces**. My Workspace page displays
    <!-- theme: info -->
    > #### Note
    >
    > All previously created workspaces are listed on the **My workspaces** page. 
    
3.	To create a new workspace, click the **Add a new workspace** button or click the **Create a new workspace** card. Create a workspace dialog box displays
4.	Enter workspace name and description
5.	From the **Product** drop-down list, select **Integrated Transaction Enrichment** and click **Create**. A new workspace is created and three tabs of your workspace, namely Summary, Credentials and Settings are visible

    <!-- theme: info -->
    > #### Note
    >
    > Currently, only one workspace can be created for Integrated Transaction Enrichment. Also, the Trial Plan is available only for a shared Premier Sandbox Environment. <br> To know our core products [click here](?path=docs/products.md "Products"). 
    
    ![image](https://user-images.githubusercontent.com/81968767/220959037-4fb7f53e-4655-4086-a0a2-8994ee505cb0.png)

Every workspace has following three sections:

* **Summary**: Displays workspace details and list of activities performed on the workspace
* **Credentials**: Lists all active API keys. From this section, you can view or download the following details of an API key:
    * Product name: _Name of the product, for example, Integrated Transaction Enrichment_    
    * Org ID: _Organization ID is required to send in all API requests under the [Request Header](#tab-know_our_standard_api_structure)_    
    * API key name: _Name of the API key_
    * API key type: _Type of API key, for example, Trial_
    * API key: _Alphanumeric value of the API key. API key is used as username while generating the access token_
    * API secret: _Alphanumeric value of the API secret. API secret is used as password while generating the access token_
    * Host URL: _Host URL path to send API requests_
      
      ![image](https://github.com/Fiserv/banking-hub/assets/85101648/3832fa3e-867f-4ffd-b8ec-857418bd4fbe)

* **Settings**: Used to modify or delete the workspace

<kbd>
    <img src="https://github.com/Fiserv/banking-hub/assets/85101648/477d8d1b-bfca-428b-84e0-b956a78eb097" />
</kbd>
              

## Generating Access Token

An access token is used to authenticate your API build and allows you to use the Fiserv APIs securely. **API key** and **API secret** values obtained from the Workspace are required to generate an access token. 

Use the API mentioned below to generate an access token using Postman.

### URL

``POST https://cert.api.fiservapps.com/fts-apim/oauth2/v2 ``


### Headers

|     Header Name      |     Description                                          |     Required      |
|---------------------|----------------------------------------------------------|---------------|
|     ``Authorization`` |    <p>Base64 encoded string representing your username and password values, appended to the text Basic as follows: </p> <p> <code> Basic <Base64 encoded username and password> </code></p> <p> **Important:** In Postman, use the **Authorization** tab to enter Username and Password values and set authentication type to **Basic Auth**. Use your **API key** as username and **API secret** as password. </p>                      |     Required    |

![image](https://user-images.githubusercontent.com/81968767/220961162-0931a990-f69a-4be7-a6bb-ab847f9464b2.png)


### Request Body

From the Body tab, select the **x-www-form-urlencoded** radio button and enter the following key-value pair:

``grant_type = client_credentials``

![image](https://user-images.githubusercontent.com/81968767/220961197-8e76ec1f-b291-4dfd-8287-c4a83b4ecf40.png)

### Response

|     Field Name      |     Description                                          |     Type      |
|---------------------|----------------------------------------------------------|---------------|
|   ``access_token``    |     Generated access token   value                       |     string    |
|``expires_in``       | <p>Time in milliseconds until the generated token is valid.</p> <p>**Note:** Once generated, the access token is valid for approximately 15 minutes. You can reuse the access token until it expires. </p> | number        |
|    ``token_type``   |     Type of access token                                 |     string    |

**Sample Response**
```
{
    "access_token": "eyJhbGciOiJSUzI1NiIsImtpZCI6IjEiLCJwaS5hdG0iOiJhYXVxIn0.eyJzY29wZSI6IiIsImNsaWVudF9pZCI6ImdxNHpvZDB6Wng3NkVPTUtKQUlQUlJUZHJHOENWNGdJIiwiaXNzIjoiaHR0cHM6Ly9mZGMtZmVkc3NvLWNhdC5maXJzdGRhdGEuY29",
    "expires_in": "899000",
    "token_type": "Bearer"
}
```


<kbd>
    <img src="https://user-images.githubusercontent.com/85101648/221878635-c859cc8d-98a3-47a3-8e57-2299af44b26e.gif" />
</kbd>

<br>
<br>

<a href="#tab-know_our_standard_api_structure" >Next - Know Our Standard API Structure</a> 


<!-- type: tab -->

# Know Our Standard API Structure 

This section describes a standard structure of request and response message of Banking Hub RESTful APIs. 

## Request Message

All API requests must contain the following components:

*	[API Method](#api-method)
* [Request URL](#request-url)
* [Access Token](#access-token)
*	[Request Header](#request-header)
*	[Request Body](#request-body)

For every API request, a response message is obtained that contains a response payload and the status of the API request.

### API Method

For security reasons, all API methods are set to POST or PUT, irrespective of the operation. 

### Request URL

Request URL is formed by appending Host URL and API path. 

<!-- theme: info -->
> **Request URL = Host URL + API path**

To get Host URL, go to API key section of your Workspace. The API path along with the method (POST or PUT) is listed under the API Explorer section of that API on Fiserv Developer Studio. 
Refer the following example to construct a request URL for [**Transaction Enrichment**](../api/?type=post&path=/transactions/v2/enrichments) API:

![image](.github/images/API_Header.png)


### Access Token

An access token is used to authenticate your API build and allows you to use the Fiserv APIs securely. Banking Hub API uses bearer access token, and API key and API secret are required to generate an access token. A generated access token is valid for approximately 15 minutes.
To generate an access token, refer to the "Generating Access Token" section under the [Before You Start](#tab-before_you_start) tab.


### Request Header
  
  
Header parameters are common for all API requests of Banking Hub APIs. Header parameters are sent as a JSON object under Integrated Transaction Enrichment header parameter.


**Sample Header Example**
```
"Content-Type":"application/json"
"Authorization":"2wyObrXPGDGFUIAmhA8G4QHYRj09P4icxZOItwa6zDdddf4kb0pddXkm73kSeOQY4:7M6Gw37xjfmvLr8W6FHJ6SwsJXipAM6I390OkNmDV4NCMt28oA2WMDubhGa9RBPW2"
"deploymentToken":"INTCSAUTH"

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