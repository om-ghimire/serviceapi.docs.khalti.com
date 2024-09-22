# Dolfin Internet

This document provides the necessary information for interacting with the Dolfin Internet service APIs, detailing the required parameters and expected responses for both fetching details and processing payments.

## Detail Fetch API

- **Request URL:** `{{base_url}}/api/servicegroup/details/dolfin-net-communication/`
- **Request Method:** POST

### Service Params

<pre><code class="json">
{
    "token": "token",
    "reference": "{{$guid}}",
    "user": "user1"
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "customer_name": "K.PATRA",
    "bill_date": "17 May, 2024",
    "invoice_number": "4494fd025d3b367ebfa1",
    "partner_code": "ARCR1RVPMU6HVNTA6Q",
    "due_date": "26 Oct, 2024",
    "bill_period": "MONTHLY",
    "packages": [
        {
            "id": 630,
            "name": "50Mbps_1 Month (FUP) [Rs. 850] 1 Month",
            "price": 50
        },
        {
            "id": 631,
            "name": "120Mbps_1 Month (FUP) [Rs. 1230] 1 Month",
            "price": 50
        },
        {
            "id": 914,
            "name": "80Mbps_1 Month (FUP) [Rs. 1080] 1 Month",
            "price": 50
        },
        {
            "id": 915,
            "name": "200Mbps_1 Month (FUP) [Rs. 1480] 1 Month",
            "price": 50
        },
        {
            "id": 916,
            "name": "300Mbps_1 Month (FUP) [Rs. 1875] 1 Month",
            "price": 50
        },
        {
            "id": 1051,
            "name": "25Mbps_Unlimited_FUP 1 Month",
            "price": 50
        },
        {
            "id": 1184,
            "name": "50Mbps_3 Months (FUP) [Rs. 2000] 3 Months",
            "price": 50
        },
        {
            "id": 1185,
            "name": "80Mbps_3 Months (FUP) [Rs. 2300] 3 Months",
            "price": 50
        },
        {
            "id": 1186,
            "name": "120Mbps_3 Months (FUP) [Rs. 2700] 3 Months",
            "price": 50
        },
        {
            "id": 1188,
            "name": "50Mbps_12 Months (FUP) [Rs. 7500] 12 Months",
            "price": 50
        },
        {
            "id": 1189,
            "name": "80Mbps_12 Months (FUP) [Rs. 9000] 12 Months",
            "price": 50
        },
        {
            "id": 1190,
            "name": "120Mbps_12 Months (FUP) [Rs. 10000] 12 Months",
            "price": 50
        }
    ],
    "amount": 50,
    "session_id": 23100,
    "status": true
}
</code></pre>

---

## Payment API

- **Request URL:** `{{base_url}}/api/servicegroup/commit/dolfin-net-communication/`
- **Request Method:** POST

### Service Params

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "package_id": "package_id",
    "session_id": "session_id"
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "status": true,
    "state": "Queued",
    "detail": "Transaction Queued",
    "message": "Your operation is in queue.",
    "credits_consumed": 1100.0,
    "credits_available": 102009144.984999,
    "extra_data": {
        "username": "joker_a",
        "mobile_number": "9818822421",
        "package": "20Mbps - 1 Month",
        "branch": "Saljhandi"
    },
    "id": 18806
}
</code></pre>

---

