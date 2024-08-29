# RC Card API Documentation

### Overview

The RC Card API allows you to process recharge operations for various service providers. The API supports different methods for each service, with specific parameters and valid amounts for each.

### Endpoint

**URL:**  
`https://uatservices.khalti.com/api/use/<method>/`  
**Type:** Single Step API  
**Request Method:** POST

### Methods

- **dishhome-erc**
- **ntc-erc**
- **utl-erc** (Deprecated)
- **smart-erc**
- **broadlink-erc**
- **nettv-erc** (Deprecated)

### Valid Amounts

1. **dishhome-erc:** 500, 1000, 2000, 3000, 4000, 5000, 6000, 7000, 9000, 10000
2. **ntc-erc:** 100, 200, 500, 1000
3. **utl-erc:** 100, 250, 500 (This service is discontinued)
4. **smart-erc:** 50, 100, 200
5. **broadlink-erc:** 570, 1300, 2600, 2260
6. **nettv-erc:** 50, 100, 200, 500, 1000 (This service is discontinued)

### Request Parameters

<pre><code class="json">
{
    "token": "<token-provided>",
    "reference": "<unique-reference>",
    "amount": "<amount>"
}
</code></pre>

## Responses
### Success Response


<pre><code class="json">
{
    "id": 165,
    "status": true,
    "state": "Success",
    "serial": "<Serial Number:string>",
    "pin": "<Pin Number:string>",
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
