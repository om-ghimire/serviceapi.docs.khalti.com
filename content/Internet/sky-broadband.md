# Sky Broadband

This document outlines the API for **Sky Broadband**, which includes functionalities for fetching available packages and processing payments. It details the request URLs, methods, parameters, and example responses for both the package fetch and payment APIs.



**Type:** Multi Step API

## 1. Package Fetch API

**Request URL:** `{{base_url}}/api/servicegroup/details/sky-broadband/`

**Request Method:** POST

### Service Params:

<pre><code class="json">
{  
    "token": "token",  
    "username": "ppoe_ashis_test",  
    "reference": "unique reference"  
}
</code></pre>

### Response:

<pre><code class="json">
{  
    "packages": [  
        {  
            "package_id": 3,  
            "package_name": "50Mbps Residential 1Month",  
            "profile": "007_50Mbps_Residential_1Month",  
            "package_slug": "50Mbps-Residential-1Month",  
            "is_referrable": 0,  
            "package_type": null,  
            "expiration_amount": null,  
            "expiration_period": null,  
            "amount": 10.0  
        },  
        {  
            "package_id": 4,  
            "package_name": "default-2Mbit-1Month",  
            "profile": "default-2Mbit-1Month",  
            "package_slug": "default-2Mbit-1Month",  
            "is_referrable": 0,  
            "package_type": "Prepaid",  
            "expiration_amount": 1,  
            "expiration_period": "Month",  
            "amount": 1000.0  
        },  
        {  
            "package_id": 5,  
            "package_name": "3-days-extension-package",  
            "profile": "3-days-extension-package",  
            "package_slug": "3-days-extension-package",  
            "is_referrable": 0,  
            "package_type": "Extension",  
            "expiration_amount": 3,  
            "expiration_period": "Day",  
            "amount": 10.0  
        }  
    ],  
    "session_id": 8319,  
    "status": true  
}
</code></pre>

## 2. Payment API

**Request URL:** `{{base_url}}/api/servicegroup/commit/sky-broadband/`

**Request Method:** POST

### Service Params:

<pre><code class="json">
{  
    "token": "token",  
    "session_id": "session_id from previous detail fetch API",  
    "amount": "amount from previous detail fetch API",  
    "package_id": "package_id from previous detail fetch API"  
}
</code></pre>

### Response:

<pre><code class="json">
{  
    "status": true,  
    "state": "Success",  
    "message": "Successfully Completed Transaction",  
    "extra_data": {},  
    "detail": "Success",  
    "credits_consumed": 10.0,  
    "credits_available": 9994745936.78663,  
    "id": 82599  
}
</code></pre>
