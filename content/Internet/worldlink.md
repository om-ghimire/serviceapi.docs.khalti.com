# **WorldLink**

## Version 2

**Type:** Multi-Step API

There are three types of users for whom this API is applicable:

1. **Package Switchable Users**  
      You will receive the package options in **package_options**.
  
    These users can switch their internet package.  
    - **Username**: `online_renew`

2.  **Package Switchable Users with Due Payment**

      You will receive the package options in **available_renew_options**.

    - **Users can switch their internet package** and need to pay any outstanding dues.
    - If the **subscribed_package_id** is the same as the **available_renew_options packageId**, **due payment** will not be added to the total payable amount.
    - If the **subscribed_package_id** is different from the **available_renew_options packageId**, the **due amount** will be added to the total payable amount.

     - **Username**: `online_due_and_package`

3. **Package Non-Switchable Users with Due Payment**  
   These users have a due payment but cannot switch their package.  
    - **Username**: `online_due_payment`

## 1. Detail Fetch API

**Request URL:** {{base_url}}/api/servicegroup/details/worldlink-v2/

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
  "subscribedPackageId": 1888314,
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
    "account_type": "PERSONAL",
    "full_name": "online_due_and_package",
    "branch": "REGION2-NBU4",
    "subscribed_package_name": "BTL 120Mbps/12mths With 1TV New Year Dhamaka 079",
    "subscribed_package_type": "Unlimited",
    "subscribed_package_id": 1888768,
    "days_remaining": 0,
    "message": "You have due payment.",
    "package_options": [],
    "vatrefund_eligible": true,
    "available_renew_options": [
        {
            "packageId": 18881068,
            "packageName": "WorldLink TurboSpeed Plus 150Mbps/12M\t",
            "packageRate": 13108,
            "packageLabel": "WorldLink TurboSpeed Plus 150Mbps/12M\t [Rs. 13108]",
            "recommendOrder": 1,
            "packageDuration": "365",
            "tvEligiblePackage": 0,
            "packageEligibility": false
        },
        {
            "packageId": 1888857,
            "packageName": "Smart Offer (1TV) 2079 200mbps/12mths",
            "packageRate": 16272,
            "packageLabel": "Smart Offer (1TV) 2079 200mbps/12mths [Rs. 16272]",
            "recommendOrder": 2,
            "packageDuration": "365",
            "tvEligiblePackage": 1,
            "packageEligibility": false
        },
        {
            "packageId": 1888767,
            "packageName": "BTL 120Mbps/3mths With 1TV New Year Dhamaka 079",
            "packageRate": 3220,
            "packageLabel": "BTL 120Mbps/3mths With 1TV New Year Dhamaka 079 [Rs. 3220]",
            "recommendOrder": 3,
            "packageDuration": "90",
            "tvEligiblePackage": 0,
            "packageEligibility": false
        },
        {
            "packageId": 1888668,
            "packageName": "Special BTL 120Mbps/mth (1TV)",
            "packageRate": 1356,
            "packageLabel": "Special BTL 120Mbps/mth (1TV) [Rs. 1356]",
            "recommendOrder": 4,
            "packageDuration": "30",
            "tvEligiblePackage": 0,
            "packageEligibility": false
        },
        {
            "packageId": 1888858,
            "packageName": "Smart Offer (1TV) 2079 250mbps/12mths",
            "packageRate": 16950,
            "packageLabel": "Smart Offer (1TV) 2079 250mbps/12mths [Rs. 16950]",
            "recommendOrder": 5,
            "packageDuration": "365",
            "tvEligiblePackage": 1,
            "packageEligibility": false
        },
        {
            "packageId": 18881115,
            "packageName": "New Smart Offer (1TV) 2081 200Mbps/6mths",
            "packageRate": 8927,
            "packageLabel": "New Smart Offer (1TV) 2081 200Mbps/6mths [Rs. 8927]",
            "recommendOrder": 6,
            "packageDuration": "180",
            "tvEligiblePackage": 0,
            "packageEligibility": false
        },
        {
            "packageId": 18881116,
            "packageName": "New smart Offer (1TV) 2081 200Mbps/24mths",
            "packageRate": 23041,
            "packageLabel": "New smart Offer (1TV) 2081 200Mbps/24mths [Rs. 23041]",
            "recommendOrder": 7,
            "packageDuration": "730",
            "tvEligiblePackage": 0,
            "packageEligibility": false
        },
        {
            "packageId": 1888768,
            "packageName": "BTL 120Mbps/12mths With 1TV New Year Dhamaka 079",
            "packageRate": 12204,
            "packageLabel": "BTL 120Mbps/12mths With 1TV New Year Dhamaka 079 [Rs.12204]",
            "tvEligiblePackage": 0,
            "packageEligibility": true,
            "packageDuration": 0,
            "recommendOrder": 0
        }
    ],
    "renew_option": true,
    "due_amount_till_now": 301,
    "due_remarks": "used 9 days of BTL 120Mbps/12mths With 1TV New Year Dhamaka 079 (1888768)",
    "first_online_payment": false,
    "amount_detail": [
        {
            "amount": 12204,
            "creditor": "worldlink",
            "particular": "Internet",
            "creditorPan": "300073250"
        }
    ],
    "amount": 12204,
    "session_id": 22906,
    "status": true
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
