# GRS Internet 

GRS Internet is an ISP.

**Type:** Multi Step API

## 1. Detail Fetch API

- **Request URL:** `{{base_url}}/api/servicegroup/details/grs/`
- **Request Method:** POST

### Service Params

<pre><code class="json">
{
    "token": "token",
    "username": "blya-test",
    "reference": "unique reference"
}
</code></pre>

### Response

<pre><code class="json">
{
    "username": "blya-test",
    "address": "Ganeshpur",
    "package": [
        {
            "package_id": "1",
            "package_name": "10Mbps",
            "amount": 1000.0,
            "valid_days": "30"
        },
        {
            "package_id": "2",
            "package_name": "20Mbps",
            "amount": 1150.0,
            "valid_days": "30"
        },
        {
            "package_id": "3",
            "package_name": "25Mbps",
            "amount": 1150.0,
            "valid_days": "30"
        },
        {
            "package_id": "4",
            "package_name": "40Mbps",
            "amount": 1650.0,
            "valid_days": "30"
        },
        {
            "package_id": "5",
            "package_name": "60Mbps",
            "amount": 1800.0,
            "valid_days": "30"
        },
        {
            "package_id": "6",
            "package_name": "30Mbps",
            "amount": 1250.0,
            "valid_days": "30"
        },
        {
            "package_id": "7",
            "package_name": "15Mbps",
            "amount": 1050.0,
            "valid_days": "30"
        },
        {
            "package_id": "8",
            "package_name": "100Mbps",
            "amount": 2550.0,
            "valid_days": "30"
        },
        {
            "package_id": "9",
            "package_name": "50Mbps",
            "amount": 1750.0,
            "valid_days": "30"
        }
    ],
    "session_id": 4603,
    "status": true
}
</code></pre>

---

## 2. Payment API

- **Request URL:** `{{base_url}}/api/servicegroup/commit/grs/`
- **Request Method:** POST

### Service Params

<pre><code class="json">
{
    "token": "token",
    "package_id": "\ Obtained from detail fetch API\  ",
    "session_id": "\ Obtained from detail fetch API\  ",
    "amount": "\ Obtained from detail fetch API\  ",
    "reference": "\ unique reference\  "
}
</code></pre>

### Response

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Success",
    "credits_consumed": 300.0,
    "credits_available": 9999711067.15,
    "id": 34081
}
</code></pre>

---

This document outlines the APIs for fetching user details and processing payments for GRS Internet services.
