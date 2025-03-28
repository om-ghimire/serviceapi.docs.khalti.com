# NTC Data Pack API Documentation

### Overview

The NTC Data Pack API allows you to:

**1.**  **Get Packages**: Retrieve a list of available NTC data and voice packs.

**2.**  **Process Payment**: Make a payment for a selected NTC data or voice pack.

### Get Packages API

**Request URL:**  
`{{base_url}}/api/servicegroup/getpackages/ntc-package/`

**Request Method:** POST

**Service Parameters:**

<pre><code class="json">
{
    "token": "token"
}
</code></pre>

## Success Response
<pre><code class="json">
{
    "status": true,
    "detail": {
        "packages": [
            {
                "priority_no": 0,
                "product_name": "NT-NT Unlimited Voice/SMS/Data",
                "amount": 20.0,
                "short_detail": "Subscription is valid for one hour from the time of purchase.",
                "package_id": "20",
                "description": "",
                "product_type": "All Pack",
                "validity": "1 Hour",
                "package_priority": 0
            },
            {
                "priority_no": 0,
                "product_name": "NT-NT 300 SMS Offer",
                "amount": 60.0,
                "short_detail": "Get NT-NT 300 SMS Offer valid for 28 days just at Rs 60",
                "package_id": "27",
                "description": "",
                "product_type": "Sms Pack",
                "validity": "28 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "120 MB Day Data Pack (6AM - 6PM)",
                "amount": 10.0,
                "short_detail": "Get 120 MB Day Data Pack (6AM - 6PM) Valid for 6AM-6PM just at Rs 10",
                "package_id": "28",
                "description": "",
                "product_type": "Data Pack",
                "validity": "1 Day",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "100 MB All Time Data Pack",
                "amount": 15.0,
                "short_detail": "Get 100 MB All Time Data Pack valid for 1 day just at Rs 15",
                "package_id": "29",
                "description": "",
                "product_type": "Data Pack",
                "validity": "1 Day",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "250 MB Day Data Pack (6AM - 6PM)",
                "amount": 15.0,
                "short_detail": "Get 250 MB Day Data Pack (6AM - 6PM) valid for 6AM-6PM just at Rs 15",
                "package_id": "30",
                "description": "",
                "product_type": "Data Pack",
                "validity": "1 Day",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "250 MB All Time Data Pack",
                "amount": 24.98,
                "short_detail": "Get 250 MB All Time Data Pack valid for 1 day just at Rs 24.98",
                "package_id": "31",
                "description": "",
                "product_type": "Data Pack",
                "validity": "1 Day",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "1GB/day Data Pack",
                "amount": 45.0,
                "short_detail": "Get 1GB/day Data Pack valid for 1 day just at Rs 45",
                "package_id": "32",
                "description": "",
                "product_type": "Data Pack",
                "validity": "1 Day",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "Unlimited Youtube Pack",
                "amount": 55.0,
                "short_detail": "Get Unlimited Youtube Pack valid for 3 days just for Rs 55",
                "package_id": "22",
                "description": "",
                "product_type": "Data Pack",
                "validity": "3 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "Unlimited Facebook Pack",
                "amount": 55.0,
                "short_detail": "Get Unlimited Facebook Pack valid for 3 days just for Rs 55",
                "package_id": "21",
                "description": "",
                "product_type": "Data Pack",
                "validity": "3 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "500 MB All Time Data Pack",
                "amount": 60.0,
                "short_detail": "Get 500 MB All Time Data Pack valid for 3 days just at Rs 60",
                "package_id": "33",
                "description": "",
                "product_type": "Data Pack",
                "validity": "3 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "800 MB All Time Data Pack",
                "amount": 99.99,
                "short_detail": "Get 800 MB All Time Data Pack valid for 7 days just at Rs 99.99",
                "package_id": "34",
                "description": "",
                "product_type": "Data Pack",
                "validity": "7 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "1GB All network+3GB (4G Network only)",
                "amount": 99.99,
                "short_detail": "Get 1GB All network+3GB (4G Network only) valid for 7 days just at Rs 99.99",
                "package_id": "35",
                "description": "",
                "product_type": "Data Pack",
                "validity": "5 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "4GB(Main Data) + 1GB/day (Facebook+Youtube) Pack",
                "amount": 179.99,
                "short_detail": "Main data is for all applications and add on data per day is for Facebook and YouTube.\nValid for 7 days",
                "package_id": "23",
                "description": "",
                "product_type": "Data Pack",
                "validity": "7 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "2GB All network+8GB (4G Network only)",
                "amount": 200.0,
                "short_detail": "Get 2GB All network+8GB (4G Network only) valid for 7 days just at Rs 200",
                "package_id": "36",
                "description": "",
                "product_type": "Data Pack",
                "validity": "7 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "2.5 GB All Time Data Pack",
                "amount": 280.0,
                "short_detail": "Get 2.5 GB Data valid for 28 days just at Rs 280",
                "package_id": "38",
                "description": "",
                "product_type": "Data Pack",
                "validity": "28 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "7 GB All Time Data Pack",
                "amount": 499.99,
                "short_detail": "Get 7 GB Data valid for 28 days just at Rs 499.99",
                "package_id": "39",
                "description": "",
                "product_type": "Data Pack",
                "validity": "28 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "10GB(Main Data) + 1GB/day (Facebook+Youtube) Pack",
                "amount": 598.99,
                "short_detail": "Main data is for all applications and add on data per day is for Facebook and YouTube.\nValid for 28 days",
                "package_id": "24",
                "description": "",
                "product_type": "Data Pack",
                "validity": "28 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "16 GB All Time Data Pack",
                "amount": 799.99,
                "short_detail": "Get 16 GB Data valid for 28 days just at Rs 799.99",
                "package_id": "40",
                "description": "",
                "product_type": "Data Pack",
                "validity": "28 Days",
                "package_priority": 0
            },
            {
                "priority_no": 1,
                "product_name": "30 GB All Time Data Pack",
                "amount": 1599.99,
                "short_detail": "Get 30 GB Data valid for 28 days just at Rs 1599.99",
                "package_id": "41",
                "description": "",
                "product_type": "Data Pack",
                "validity": "28 Days",
                "package_priority": 0
            }
        ]
    }
}
</code></pre>



##  Payment API

**Request URL:**
``{{base_url}}/api/use/ntc-package/``

**Request Method:** `POST`

**Service Parameters:**

<pre><code class="json">

{
    "token": "token",
    "package_id": "package_id",
    "amount": "amount",
    "reference":"{{$guid}}",
    "number":"9876541230"
}
</code></pre>
### Success Response:

<pre><code class="json">

{
    "status": true,
    "state": "Success",
    "detail": {
        "transaction_id": "transaction_id",
        "amount": "amount",
        "package_id": "package_id",
        "status": "success"
    }
}
</code></pre>
### Error Response:

<pre><code class="json">

{
    "status": false,
    "detail": "Error message describing what went wrong."
}
</code></pre>