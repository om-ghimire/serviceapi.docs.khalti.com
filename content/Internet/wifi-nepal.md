# Wifi Nepal API

Wifi Nepal provides a multi-step API for managing internet service subscriptions and payments.

## Type: Multi Step API

### 1. Detail Fetch API

This endpoint retrieves detailed information about a user's Wifi Nepal account, including due payments and package details.

#### Request

- **Request URL:** `{{base_url}}/api/servicegroup/details/wifi-nepal/`
- **Request Method:** `POST`
- **Service Params:**

<pre><code class="json">
{
    "token": "token",
    "username": "username",
    "reference": "unique reference",
    "service_slug": "wifi-nepal-v2"
}
</code></pre>

#### Response

The response contains the user's details, subscription package, due amount, and remaining days.

<pre><code class="json">
{
    "name": "Kalpana Dahal",
    "user_id": "test10_wifinepal",
    "amount": 6215,
    "subscribed_package_name": "Master Plan-50mbps/12mths",
    "subscription_type": "RETAIL",
    "days_remaining": "353",
    "message": "You have due payment.",
    "amount_detail": [
        {
            "particular": "Internet",
            "amount": 5085
        },
        {
            "particular": "Equipment Rental Charges",
            "amount": 1130
        }
    ],
    "session_id": 548,
    "status": true
}
</code></pre>

### 2. Payment API

This endpoint processes the payment for the user's Wifi Nepal account.

#### Request

- **Request URL:** `{{base_url}}/api/servicegroup/commit/wifi-nepal/`
- **Request Method:** `POST`
- **Service Params:**

<pre><code class="json">
{
    "amount": "1808",
    "session_id": "21820",
    "reference": "{{$guid}}",
    "token": "{{token}}",
    "service_slug": "wifi-nepal-v2"
}
</code></pre>

#### Response

The response confirms the transaction and provides invoice details.

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": {
        "invoiceNumber": "gs-366/2079.080",
        "taxableAmount": "5500",
        "vatAmount": "715"
    },
    "credits_consumed": 6215,
    "credits_available": 9791703.64,
    "id": 58743
}
</code></pre>
