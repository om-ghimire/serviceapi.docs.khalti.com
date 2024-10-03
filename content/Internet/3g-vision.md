# 3G Vision

This document outlines the API for **3G Vision**, which includes two main functionalities: retrieving available packages and processing payments. It details the request URLs, methods, parameters, and example responses for both the package retrieval and payment APIs.



## Get Packages API

**Request URL:** `{{base_url}}/api/servicegroup/getpackages/three-g-vision/`

**Request Method:** POST

### Service Params:

<pre><code class="json">
{  
    "token": "token",  
    "reference": "unique reference"  
}
</code></pre>

### Response:

<pre><code class="json">
{  
    "status": true,  
    "detail": {  
        "packages": [  
            {  
                "label": "5 Mbps unlimited - Internet",  
                "value": "5 Mbps unlimited - Internet"  
            },  
            {  
                "label": "10 Mbps unlimited - Internet",  
                "value": "10 Mbps unlimited - Internet"  
            },  
            {  
                "label": "15 Mbps unlimited - Internet",  
                "value": "15 Mbps unlimited - Internet"  
            },  
            {  
                "label": "30 Mbps unlimited - Internet",  
                "value": "30 Mbps unlimited - Internet"  
            },  
            {  
                "label": "75 Mbps unlimited - Internet",  
                "value": "75 Mbps unlimited - Internet"  
            },  
            {  
                "label": "Basic Package - Tv",  
                "value": "Basic Package - Tv"  
            },  
            {  
                "label": "Basic Plus Package - Tv",  
                "value": "Basic Plus Package - Tv"  
            },  
            {  
                "label": "Premium Package - Tv",  
                "value": "Premium Package - Tv"  
            }  
        ]  
    }  
}
</code></pre>

## Payment API

**Request URL:** `{{base_url}}/api/use/three-g-vision/`

**Request Method:** POST

### Service Params:

<pre><code class="json">
{  
    "token": "{{live}}",  
    "reference": "{{$guid}}",  
    "name": "udeep",  
    "contact_number": "9849324652",  
    "user_id": "aoubeceoa",  
    "amount": 100,  
    "package": "5 Mbps unlimited - Internet",  
    "remarks": "This is an optional field"  
}
</code></pre>

### Response:

<pre><code class="json">
{  
    "status": true,  
    "state": "Queued",  
    "detail": "Transaction Queued",  
    "message": "Your operation is in queue.",  
    "credits_consumed": 100.0,  
    "credits_available": "**********",  
    "extra_data": {  
        "name": "udeep",  
        "contact_number": "9849324652",  
        "user_id": "aoubeceoa",  
        "package": "5 Mbps unlimited - Internet",  
        "remarks": "This is an optional field"  
    },  
    "id": 20274  
}
</code></pre>
