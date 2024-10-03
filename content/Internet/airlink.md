# Airlink Communication

This document provides details for the **Airlink Communication** Single Step API, which is used for processing payments related to their services. It includes the request URL, method, parameters, and example responses.



Airlink is an ISP.

## Type: Single Step API

### Payment API:

**Request URL:** `{{base_url}}/api/use/airlink-communication/`

**Request Method:** POST

### Service Params:

<pre><code class="json">
{
    "token": "token",
    "mobile_number": "user-mobile-number",
    "username": "sashant",
    "address": "bhaktapur",
    "amount": 10,
    "reference": "unique reference"
}
</code></pre>

### Response:

<pre><code class="json">
{
    "status": true,
    "state": "Queued",
    "detail": "Transaction Queued",
    "message": "Your operation is in queue.",
    "credits_consumed": 10.0,
    "credits_available": 9999767335.42,
    "extra_data": {
        "mobile_number": "9843007232",
        "username": "sashant",
        "address": "bhaktapur"
    },
    "id": 32438
}
</code></pre>
