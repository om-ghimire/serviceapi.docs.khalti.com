# PSTN (Landline) API Documentation

### Overview

The PSTN (Landline) API allows you to process landline recharge operations. This API supports a single request method and requires specific parameters for successful processing.

### Endpoint

**URL:**   `{{base_url}}/api/use/landline/`  
**Type:** Single Step API  
**Request Method:** POST

### Request Parameters

- **number**: 8-digit number (area code without 0 and landline number)  
  *Example:* `15522942`  
  *Regex Pattern:* `(\[0-9\]{8})`  
  *Error Message:* "Invalid LandLine number"
  
- **token**: `<token-provided>`
- **reference**: `<unique-reference>`
- **amount**: `<amount>`  
  *Amount should be between Rs.10 and Rs.10,000*

### Request Example

<pre><code class="json">
{
    "token": "token-provided",
    "reference": "unique-reference",
    "amount": "amount",
    "number": "number"
}
</code></pre>
## Responses
### Success Response

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

### Unsuccessful Response

<pre><code class="json">
{
    "error_code": "1010",
    "message": "Validation error",
    "status": false,
    "error_data": {
        // Present for validation errors (codes 1010, 1011) specifying errors corresponding to fields
    },
    "details": "<empty for validation error, error details(string) for other errors>"
}
</code></pre>