
# First Link

This document outlines the API for **First Link**, which includes functionalities for retrieving user details, getting package rates, and processing payments. It includes request URLs, methods, parameters, and example responses for each API.


## User Detail API

**Request URL:** `{{base_url}}/api/servicegroup/details/firstlink/`

**Request Method:** POST

### Service Params:

<pre><code class="json">
{  
    "token": "{{token}}",  
    "reference": "{{$guid}}",  
    "username": "url_ramesh_kafle"
}
</code></pre>

### Response:

<pre><code class="json">
{  
    "email": "ramesh@firstlink.net.np",  
    "user_identifier": "2",  
    "session_id": 55,  
    "status": true  
}
</code></pre>

## Get Packages API

**Request URL:** `{{base_url}}/api/servicegroup/getpackagerates/firstlink/`

**Request Method:** POST

### Service Params:

<pre><code class="json">
{  
    "token": "{{token}}",  
    "session_id": 55  
}
</code></pre>

### Response:

<pre><code class="json">
{  
    "active_internet_services": [  
        {  
            "mac": "A4BE2BB9926C",  
            "description": "Fiberhome 40Mbps-1Month",  
            "status": "active",  
            "unit_price": "1921.0000"  
        }  
    ],  
    "tariff": {  
        "title": "Fiberhome 40Mbps-1Month",  
        "service_name": "Fiberhome 40Mbps-1Month",  
        "billing_days_count": "30"  
    },  
    "session_id": 55,  
    "status": true  
}
</code></pre>

## Payment API

**Request URL:** `{{base_url}}/api/servicegroup/commit/firstlink/`

**Request Method:** POST

### Service Params:

<pre><code class="json">
{  
    "token": "{{token}}",  
    "amount": 1921,  
    "session_id": 4,  
    "comment": "Optional"  
}
</code></pre>

### Response:

<pre><code class="json">
{  
    "status": true,  
    "state": "Queued",  
    "detail": "Transaction Queued [Exception in Payment]",  
    "message": "Your operation is in queue.",  
    "credits_consumed": 1921.0,  
    "credits_available": "**********",  
    "extra_data": {},  
    "id": 20276  
}
</code></pre>
