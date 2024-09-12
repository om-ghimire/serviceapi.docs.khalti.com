# **WorldLink**

## Version 2

**Type:** Multi-Step API

There are three types of users for whom this API is applicable:

1. **Package Switchable Users**
   Users have access to switch the internet package.
   - **username:** `online_renew`

2. **Package Switchable Users with Due Payment**
   Users make payments for the due amount of the internet and have access to switch packages. Both due and package switch charges will be applied in case of a package change. If users do not wish to change the package, the due payment is not necessary.
   - **username:** `online_due_and_package`

3. **Package Non-Switchable Users with Due Payment**
   - **username:** `online_due_payment`

## 1. Detail Fetch API

**Request URL:** [{{base_url}}/api/servicegroup/details/worldlink-v2/](https://example.com/api/servicegroup/details/worldlink-v2/)

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{ 
  "token": "token", 
  "reference": "<unique reference>", 
  "username": "online_renew/online_due_payment" 
}
</code></pre>

**Response:**

Responses vary depending on the type of user. 

### Response for Package Switchable Users

**Example Response:**

<pre><code class="json">
{  
  "username": "online_renew",  
  "full_name": "Online Renew",  
  "subscribed_package_name": "Value Standard 25mbps/3mths 1TV (Renew)",  
  "subscribed_package_type": "Unlimited",  
  "days_remaining": 0,  
  "message": "You have due payment.",  
  "package_options": [  
    {  
      "packageId": 1888117,  
      "packageName": "Fiber Smart home 2019-25mbps/3 mths(Renew)",  
      "packageRate": 4915,  
      "packageLabel": "Fiber Smart home 2019-25mbps/3 mths(Renew) [Rs. 4915]"  
    },  
    {  
      "packageId": 1888314,  
      "packageName": "Value Standard 25mbps/3mths 1TV (Renew)",  
      "packageRate": 4915,  
      "packageLabel": "Value Standard 25mbps/3mths 1TV (Renew) [Rs. 4915]"  
    },  
    {  
      "packageId": 1888118,  
      "packageName": "Fiber Smart home 2019-40mbps/3 mths(Renew)",  
      "packageRate": 5932,  
      "packageLabel": "Fiber Smart home 2019-40mbps/3 mths(Renew) [Rs. 5932]"  
    },  
    {  
      "packageId": 1888119,  
      "packageName": "Fiber Smart home 2019-60mbps/3 mths(Renew)",  
      "packageRate": 8475,  
      "packageLabel": "Fiber Smart home 2019-60mbps/3 mths(Renew) [Rs. 8475]"  
    },  
    {  
      "packageId": 1888123,  
      "packageName": "Fiber Smart home 2019-25mbps/12mths(Renew)",  
      "packageRate": 16272,  
      "packageLabel": "Fiber Smart home 2019-25mbps/12mths(Renew) [Rs. 16272]"  
    },  
    {  
      "packageId": 1888124,  
      "packageName": "Fiber Smart home 2019-40mbps/12mths(Renew)",  
      "packageRate": 19097,  
      "packageLabel": "Fiber Smart home 2019-40mbps/12mths(Renew) [Rs. 19097]"  
    },  
    {  
      "packageId": 1888125,  
      "packageName": "Fiber Smart home 2019-60mbps/12mths(Renew)",  
      "packageRate": 28250,  
      "packageLabel": "Fiber Smart home 2019-60mbps/12mths(Renew) [Rs. 28250]"  
    }  
  ],  
  "renew_option": false,  
  "first_online_payment": false,  
  "amount_detail": [  
    {  
      "particular": "Internet",  
      "amount": 4915  
    }  
  ],  
  "amount": 4915,  
  "session_id": 109,  
  "status": true  
}
</code></pre>

### Response for Package Switchable Users with Due Payment

**Example Response:**

<pre><code class="json">
{  
  "username": "online_due_and_package",  
  "full_name": "Online due and package",  
  "branch": "MANBHAWAN",  
  "subscribed_package_name": "TV ma YouTube 25mbps/12mths 1TV (Renew)",  
  "subscribed_package_type": "Unlimited",  
  "days_remaining": 0,  
  "message": "You have due payment.",  
  "renew_option": true,  
  "due_amount_till_now": 401,  
  "first_online_payment": false,  
  "amount_detail": [  
    {  
      "particular": "Internet",  
      "amount": 16272  
    }  
  ],  
  "amount": 16272,  
  "available_renew_options": [  
    {  
      "label": "30Mbps/12mths SPECIAL OFFER 2077 (1TV) [Rs. 16950]",  
      "value": 1888349,  
      "amount": 16950  
    },  
    {  
      "label": "40Mbps/12mths SPECIAL OFFER 2077 (2TV) [Rs. 19775]",  
      "value": 1888352,  
      "amount": 19775  
    },  
    {  
      "label": "60Mbps/12mths SPECIAL OFFER 2077 (3TV) [Rs. 24860]",  
      "value": 1888355,  
      "amount": 24860  
    }  
  ],  
  "package_options": [],  
  "log_idx": "RMkd5PoS49GBWAvWKme8nU"  
}
</code></pre>

### Response for Package Non-Switchable Users with Due Payment

**Example Response:**

<pre><code class="json">
{  
  "username": "online_due_payment",  
  "full_name": "Online Due Payment",  
  "branch": "MANIGRAM",  
  "subscribed_package_name": "Value Standard 25mbps/3mths 1TV (Renew)",  
  "subscribed_package_type": "Unlimited",  
  "days_remaining": 0,  
  "message": "You have due payment.",  
  "package_options": [],  
  "renew_option": false,  
  "first_online_payment": false,  
  "amount_detail": [  
    {  
      "particular": "Internet",  
      "amount": 4950  
    }  
  ],  
  "amount": 4950,  
  "session_id": 224,  
  "status": true  
}
</code></pre>

## 2. Payment API

**Request URL:** [{{base_url}}/api/servicegroup/commit/worldlink-v2/](https://khalti.com/api/v2/service/use/bus-sewa/search/api/servicegroup/commit/worldlink-v2/)

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{ 
  "token": "token", 
  "session_id": "<session_id from detail step>", 
  "amount": 4950,  
  "package_id": "<Package Id from the detail step>",  // OPTIONAL - Required when a package is selected  
  "reference": "<unique reference id>" 
}
</code></pre>

**Response:**

**Success Response:**

<pre><code class="json">
{  
  "status": true,  
  "state": "Success",  
  "message": "Successfully Completed Transaction",  
  "extra_data": {},  
  "detail": "Transaction successful",  
  "id": 5033  
}
</code></pre>

**Error Response:**

<pre><code class="json">
{  
  "status": false,  
  "error_code": "4000",  
  "message": "Can't fulfill request",  
  "error": "client_error",  
  "details": "Customer not found.",  
  "error_data": {},  
  "state": "Error"  
}
</code></pre>
