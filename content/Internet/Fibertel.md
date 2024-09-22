# Fibertel Fibernet

This document outlines the API for initiating a transaction with Fibertel Fibernet, including the required parameters and expected response format.

**Type:** Single Step API

### Request Details

- **Request URL:** `{{base_url}}/api/use/fibertel-fibernet/`
- **Request Method:** POST

#### Service Params

<pre><code class="json">
{
    "token": "{{live}}",
    "username": "abin",
    "contact_number": "9843666888",
    "package": "Residential Plan 1 Month 30 Mbps",  // User Input
    "amount": 15501,  // User Input
    "reference": "sky12",
    "remarks": "TEST"
}
</code></pre>

### Response

<pre><code class="json">
{
    "status": true,
    "state": "Queued",
    "detail": "Transaction Queued",
    "message": "Your operation is in queue.",
    "credits_consumed": 15501.0,
    "credits_available": 101197089.864999,
    "extra_data": {
        "username": "abin",
        "contact_number": "9843666888",
        "package": "Residential Plan 1 Month 30 Mbps",
        "remarks": "TEST",
        "name": "ABin"
    },
    "id": 20211
}
</code></pre>