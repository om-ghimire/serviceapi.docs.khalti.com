# Net Max Service

## Overview

An overview of the Net Max service APIs, including details on how to fetch customer subscription information and process payments. It covers the necessary request parameters, expected responses, and notes for handling dues.

---

## Fetch API

### Detail Fetch API

- **Request URL:** `{{base_url}}/api/servicegroup/details/net-max/`
- **Request Method:** POST

#### Service Params

<pre><code class="json">
{
    "token": "token",
    "username": "new/active/expired",
    "reference": "Unique reference"
}
</code></pre>

#### Response Example

<pre><code class="json">
{
    "customer": {
        "username": "9779803074977",
        "name": "koshish bortaula",
        "mobile": "",
        "status": "Expired"
    },
    "current_subscription": {
        "package": "NET+TV - 30Mbps",
        "end_date": "2021-01-31",
        "status": "Expired"
    },
    "due": {
        "amount": "0",
        "message": "Due Amount is NIL"
    },
    "packages": [
        {
            "package_id": "1-4412-8-1",
            "package_name": "NET+TV - 30Mbps - 1 Month(s)",
            "amount": 1850,
            "current": false
        },
        {
            "package_id": "1-4412-8-3",
            "package_name": "NET+TV - 30Mbps - 3 Month(s)",
            "amount": 5550,
            "current": false
        },
        {
            "package_id": "1-4412-8-6",
            "package_name": "NET+TV - 30Mbps - 6 Month(s)",
            "amount": 9250,
            "current": false
        },
        {
            "package_id": "1-4412-8-12",
            "package_name": "NET+TV - 30Mbps - 12 Month(s)",
            "amount": 18500,
            "current": true
        }
    ],
    "session_id": 8,
    "status": true
}
</code></pre>

**Note:** If there is a due amount, it will be displayed separately without summing it with the package amount. Package amounts may vary for different users if there are dues.

---

## Payment API


**Request URL:** `{{base_url}}/api/servicegroup/commit/net-max/`
**Request Method:** POST

#### Service Params

<pre><code class="json">
{
    "token": "token",
    "package_id": "1-4412-8-1",
    "amount": "1850",
    "session_id": "8",
    "reference": "Unique reference"
}
</code></pre>

#### Response Example

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Payment made successfully. Account will be activated in few minutes",
    "credits_consumed": 1850.0,
    "credits_available": 986190.0,
    "id": 60959
}
</code></pre>