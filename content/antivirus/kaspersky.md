# Kaspersky Antivirus

This document outlines the API for **Kaspersky Antivirus**, which includes functionalities for fetching package details and processing payments. It provides request URLs, methods, parameters, and example responses for both the package details fetch and payment APIs.

# Kaspersky Antivirus

**Type:** Multi Step API

## 1. Package Details Fetch API

**Request URL:** `{{base_url}}/api/servicegroup/details/antivirus-service/`

**Request Method:** POST

### Service Params:

<pre><code class="json">
{  
    "token": "token"  
}
</code></pre>

### Response:

<pre><code class="json">
{  
    "status": true,  
    "detail": [  
        {  
            "name": "Kaspersky Standard 1 Device 1 Year",  
            "product_code": "KS-1D-1Y",  
            "price": 700  
        },  
        {  
            "name": "Kaspersky Plus 1 Device 1 Year",  
            "product_code": "KP-1D-1Y",  
            "price": 1400  
        },  
        {  
            "name": "Kaspersky Standard 3 Devices 1 Year",  
            "product_code": "KS-3D-1Y",  
            "price": 1400  
        },  
        {  
            "name": "Kaspersky Premium 1 Device 1 Year",  
            "product_code": "KPR-1D-1Y",  
            "price": 2100  
        },  
        {  
            "name": "Kaspersky Plus 3 Devices 1 Year",  
            "product_code": "KP-3D-1Y",  
            "price": 2100  
        },  
        {  
            "name": "Kaspersky Premium 3 Devices 1 Year",  
            "product_code": "KPR-3D-1Y",  
            "price": 2800  
        }  
    ]  
}
</code></pre>

## 2. Payment API

**Request URL:** `{{base_url}}/api/servicegroup/commit/antivirus-service/`

**Request Method:** POST

### Service Params:

<pre><code class="json">
{  
    "token": "{{token}}",  
    "product_code": "KS-1D-1Y",  
    "amount": 700,  
    "name": "Dev Dev",  
    "email": "Dev Dev",  
    "mobile": "1234567899",  
    "reference": "{{$guid}}"  
}
</code></pre>

### Response:

<pre><code class="json">
{  
    "status": true,  
    "state": "Success",  
    "message": "Successfully Completed Transaction",  
    "extra_data": {},  
    "detail": "Transaction Successful",  
    "credits_consumed": 700,  
    "credits_available": 1e+32,  
    "id": 117671  
}
</code></pre>
