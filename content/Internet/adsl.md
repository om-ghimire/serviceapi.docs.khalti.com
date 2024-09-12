# **ADSL**

## Overview

The ADSL API allows you to perform operations related to both Unlimited and Volume Based ADSL services. Depending on your choice, you can submit requests for ADSL services using the provided API endpoints. This API requires parameters such as a token, a unique reference, the amount, and the landline number to process the request.

## Type: Single Step API  

### URL:

- **Unlimited:** `{{base_url}}/api/use/adsl-ul/`
- **Volume Based:** `{{base_url}}/api/use/adsl-vb/`

### Service Params:

- **number:** 8-digit number (area code without 0 and landline number), e.g., 15522942
- **token:** Your authentication token
- **reference:** A unique reference for the transaction
- **amount:** The amount to be processed
- **number:** The landline number in the required format

### Valid Amounts for Both Unlimited & Volume Based:

- 9 < Amount < 10001

### Regex:

<pre><code class="json">
[  
  {  
    "name": "LandLine",  
    "slug": "",  
    "pattern": "([0-9]{8})",  
    "error_message": "Invalid LandLine number"  
  }  
]
</code></pre>

### Request:

<pre><code class="json">
{  
  "token": "token-provided",  
  "reference": "unique-reference",  
  "amount": "amount",  
  "number": "number"  
}
</code></pre>

### Response:

#### Success Response:

<pre><code class="json">
{  
  "id": 165,  
  "credits_consumed": 10.0,  
  "status": true,  
  "state": "Queued",  
  "message": "Your operation has been submitted for processing.",  
  "credits_available": 1170  
}
</code></pre>

#### Unsuccessful Response:

<pre><code class="json">
{  
  "error_code": "1010",  
  "message": "Validation error",  
  "status": false,  
  "error_data": <json: *present for validation error(codes 1010, 1011) specifying errors corresponding to fields*>,  
  "details": "*<empty for validation error, error details(string) for other errors>*"  
}
</code></pre>

### Note:

Check the `status` key in the response to verify the response. If `status` is `false`, there is an issue with the request, and you should correct it. If `status` is `true`, the request is successfully submitted but is subject to third-party provider processing. If the `state` is `Queued`, the request is being sent to the third-party provider, and you will receive an update on the final status (success or failure) via our DLR callback.

### DLR Sample:

<pre><code class="json">
{  
  "reference": "Unique id sent by you",  
  "amount": "amount",  
  "status": "status",  
  "detail": "detail regarding the service"  
}
</code></pre>
