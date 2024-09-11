# P & G Network API

## Overview

This document provides details on the APIs for the P & G Network service. It includes endpoints for fetching package information and processing payments.

### Package Fetch API

**Request URL:** `{{base_url}}/api/servicegroup/getpackages/png-network/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "package_type": "tv"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "detail": {
        "packages": [
            {
                "package_name": "Silver 1TV - 1 Month",
                "amount": 300.0
            },
            {
                "package_name": "Silver 1TV - 3 Month",
                "amount": 900.0
            },
            {
                "package_name": "Silver 1TV - 6 Month",
                "amount": 1800.0
            },
            {
                "package_name": "Silver 1TV - 12 Month",
                "amount": 3600.0
            },
            {
                "package_name": "Gold HD 1TV - 1 Month",
                "amount": 400.0
            },
            {
                "package_name": "Gold HD 1TV - 3 Month",
                "amount": 1200.0
            },
            {
                "package_name": "Gold HD 1TV - 6 Month",
                "amount": 2400.0
            },
            {
                "package_name": "Gold HD 1TV - 12 Month",
                "amount": 4800.0
            },
            {
                "package_name": "Platinum Full HD 1TV - 1 Month",
                "amount": 500.0
            },
            {
                "package_name": "Platinum Full HD 1TV - 3 Month",
                "amount": 1500.0
            },
            {
                "package_name": "Platinum Full HD 1TV - 6 Month",
                "amount": 3000.0
            },
            {
                "package_name": "Platinum Full HD 1TV - 12 Month",
                "amount": 6000.0
            }
        ]
    }
}
</code></pre>

### Payment API

**Request URL:** `{{base_url}}/api/use/png-network/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{TOKEN}}",
    "reference": "{{$guid}}",
    "package": "Silver 1TV - 1 Month",
    "amount": 300,
    "user_name": "abcdef",  // Either 6 characters or 000{6 characters}
    "contact_number": "9849324652",
    "customer_name": "abc"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Queued",
    "detail": "Transaction Queued",
    "message": "Your operation is in queue.",
    "credits_consumed": 300.0,
    "credits_available": 106470895.045,
    "extra_data": {
        "package": "Silver 1TV - 1 Month",
        "user_name": "0000abcdef",
        "contact_number": "9849324652",
        "customer_name": "abc"
    },
    "id": 8230
}
</code></pre>
