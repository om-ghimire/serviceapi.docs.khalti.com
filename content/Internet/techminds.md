# Techminds API

The Techminds API provides endpoints for fetching user details and processing payments.

## Type: Multi Step API

### 1. User Detail API

- **URL:** `{{base_url}}/api/servicegroup/details/techminds/`
- **Method:** `POST`

#### Service Parameters

The request must include the following parameters:

<pre><code class="json">
{
    "token": "token",
    "request_id": "lionschowk",
    "reference": "techminds123"
}
</code></pre>

### Response: User Details

#### Success Response

<pre><code class="json">
{
    "data": {
        "customer_name": "Kamal Raj Paudyal",
        "expiration": "Dec 28 2024",
        "mobile_number": "9855059124",
        "previous_balance": 256,
        "email": "kamal@technolinx.com.np",
        "monthly_charge": "1350"
    },
    "status": true,
    "session_id": 8,
    "available_plans": {
        "180 Days": 8100,
        "90 Days": 4050,
        "30 Days": 1350,
        "15 Days": 675,
        "60 Days": 2700
    }
}
</code></pre>

---

### 2. Payment API

- **URL:** `{{base_url}}/api/servicegroup/commit/techminds/`
- **Method:** `POST`

#### Service Parameters

The request must include the following parameters:

<pre><code class="json">
{
    "request_id": "lionschowk",
    "session_id": 7,
    "reference": "reference123",
    "token": "TEST:O7QxjFcdueNzAh9aBOsD",
    "amount": 1350
}
</code></pre>

### Response: Payment

#### Success Response

<pre><code class="json">
{
    "id": 2209,
    "status": true,
    "message": "Successfully Completed Transaction",
    "state": "Success",
    "detail": "Transaction successful",
    "extra_data": {}
}
</code></pre>
