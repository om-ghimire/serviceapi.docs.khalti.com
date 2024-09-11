# Jagriti Cable Network API 


## Overview

This document details the APIs for the Jagriti Cable Network service, including endpoints for fetching package information and processing payments.

### Package Fetch API

**Request URL:** `{{base_url}}/api/servicegroup/getpackages/jagriti-national-cable-network/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "type": "tv"  // "tv" for TV services, "internet" for ISP services
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "detail": {
        "packages": [
            {
                "package_name": "TV HD Package - 1Month - 1TV",
                "amount": 350
            },
            {
                "package_name": "TV HD Package - 3Month - 1TV",
                "amount": 1050
            },
            {
                "package_name": "TV HD Package - 6Month - 1TV",
                "amount": 1900
            },
            {
                "package_name": "TV HD Package - 12Month - 1TV",
                "amount": 3600
            },
            {
                "package_name": "TV HD Package - 1Month - 2TV",
                "amount": 525
            },
            {
                "package_name": "TV HD Package - 3Month - 2TV",
                "amount": 1575
            },
            {
                "package_name": "TV HD Package - 6Month - 2TV",
                "amount": 2800
            },
            {
                "package_name": "TV HD Package - 12Month - 2TV",
                "amount": 5250
            },
            {
                "package_name": "TV HD Package - 1Month - 3TV",
                "amount": 700
            },
            {
                "package_name": "TV HD Package - 3Month - 3TV",
                "amount": 2100
            },
            {
                "package_name": "TV HD Package - 6Month - 3TV",
                "amount": 3700
            },
            {
                "package_name": "TV HD Package - 12Month - 3TV",
                "amount": 6900
            }
        ]
    }
}
</code></pre>

### Payment API

**Request URL:** `{{base_url}}/api/use/jagriti-national-cable-network/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{TOKEN}}",
    "reference": "{{$guid}}",
    "package": "TV HD Package - 1Month - 1TV",
    "amount": 350,
    "stb_or_cas_id": "0123456789012345",  // Should be either 11 numbers or 16 numbers
    "customer_name": "abc",
    "old_ward_number": 10,
    "customer_id": "1245",  // Optional
    "mobile_number_1": "9841111111",
    "mobile_number_2": "9841111111"  // Optional
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Queued",
    "detail": "Transaction Queued",
    "message": "Your operation is in queue.",
    "credits_consumed": 350.0,
    "credits_available": 106470545.045,
    "extra_data": {
        "package": "TV HD Package - 1Month - 1TV",
        "customer_name": "12345",
        "old_ward_number": "10",
        "stb_or_cas_id": "0123456789012345",
        "customer_id": "Optional",
        "mobile_number_1": "9849324652",
        "mobile_number_2": "9818822421"
    },
    "id": 8234
}
</code></pre>
