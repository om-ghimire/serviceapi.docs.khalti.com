# Web Network API

The Web Network API allows users to fetch details and make payments for web network services.

## Type: Multi Step API

### 1. Get Details

- **URL:** {{base_url}}/api/servicegroup/details/web-network
- **Method:** `POST`

#### Service Parameters

The request must include the following parameters:

<pre><code class="json">
{
    "token": "token",
    "request_id": "anjudvt_fiber",
    "reference": "unique reference identifier"
}
</code></pre>

#### Response

Upon successful request, the API will return a response in the following format:

<pre><code class="json">
{
    "request_id": "anjudvt_fiber",
    "amount": 7150,
    "response_message": "",
    "properties": {
        "name": "Anju Kc",
        "address": "Nayamil, Rupandehi",
        "package": "Fiber Plan",
        "duration": "8"
    },
    "session_id": 8795,
    "status": true
}
</code></pre>

### 2. Payment

- **URL:** {{base_url}}/api/servicegroup/commit/web-network/
- **Method:** `POST`

#### Service Parameters

The request must include the following parameters:

<pre><code class="json">
{
    "amount": "amount from get details API",
    "session_id": "session id from get details API",
    "reference": "unique reference",
    "token": "token"
}
</code></pre>

#### Response

Upon successful transaction, the API will return a response in the following format:

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Success",
    "credits_consumed": 7150,
    "credits_available": 999999998110797.6,
    "id": 62819
}
</code></pre>
