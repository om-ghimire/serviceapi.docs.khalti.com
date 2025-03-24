# Kriti Darshan

This document provides details for the **Kriti Darshan** Single Step API, including the request URL, method, parameters, and example responses. The API allows users to initiate transactions and provides feedback on the status of those transactions.
**Single Step API**

**Request URL:** `{{base_url}}/api/use/kriti-darshan/`

**Request Method:** POST

## Service Params:

<pre><code class="json">
{  
    "full_name": "udeep shrestha",  
    "amount": 2000,  
    "token": "{{LIVE_TOKEN}}",  
    "reference": "{{$guid}}",  
    "address": "Madhyapur Thimi",  
    "mobile_number": "016632588"  
}
</code></pre>

**Response:**

<pre><code class="json">
{  
    "status": true,  
    "state": "Queued",  
    "detail": "Transaction Queued",  
    "message": "Your operation is in queue.",  
    "credits_consumed": 2000.0,  
    "credits_available": 101194530.874999,  
    "extra_data": {  
        "full_name": "udeep shrestha",  
        "address": "Madhyapur Thimi",  
        "mobile_number": "016632588"  
    },  
    "id": 20270  
}
</code></pre>
