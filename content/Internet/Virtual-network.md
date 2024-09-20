# Virtual Network API

The Virtual Network API allows users to make payments for virtual network services.

## Type: Single Step API

### Endpoint

- **URL:** `{{base_url}}/api/use/virtual-network/`
- **Method:** `POST`

### Service Parameters

The request must include the following parameters:

<pre><code class="json">
{
    "token": "token",
    "username": "Username, eg: khaltiUser",
    "mobile_number": "9818766122",
    "amount": 100,  // Minimum Amount 100
    "reference": "virtualnetwork1"
}
</code></pre>

### Regex Validation

For the `username` parameter, the following regex validation applies:

<pre><code class="json">
[
    {
        "name": "Username",
        "slug": "",
        "pattern": "([a-zA-Z0-9_]+)",
        "error_message": "Invalid Username"
    }
]
</code></pre>

### Response

Upon successful operation, the API will return a response in the following format:

<pre><code class="json">
{
    "status": true,
    "id": 1266,
    "credits_available": 9200.0,
    "message": "Your operation is in queue.",
    "state": "Queued",
    "credits_consumed": 100.0
}
</code></pre>
