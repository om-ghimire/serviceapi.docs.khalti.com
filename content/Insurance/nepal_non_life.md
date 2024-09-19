# Nepal Life s Insurance

## Overview

The Nepal Insurance API provides a multi-step process for fetching insurance details and processing payments. This API enables users to retrieve information about available policies, branches, and insurance types, and allows for the submission of payment requests for chosen insurance plans.

## **Type: Multi Step API**

### 1. **Detail Fetch**

**Request URL:** `{{base_url}}/api/servicegroup/info/nepal-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "policies": [
        {
            "label": "Endorsement",
            "value": "1"
        },
        {}
    ],
    "insurance_types": [
        {
            "label": "Motor/ Vehicle Insurance",
            "value": "1"
        },
        {
            "label": "Micro/ Agriculture Insurance",
            "value": "22"
        }
    ],
    "branches": [
        {
            "label": "Abukhaireni",
            "value": "1"
        },
        {
            "label": "Tulsipur",
            "value": "51"
        }
    ]
}
</code></pre>

---

### 2. **Payment API**

**Request URL:** `{{base_url}}/api/servicegroup/commit/nepal-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "policy_type": "{{policy value}}",    // from detail fetch API
    "branch": "{{branch value}}",          // from detail fetch API
    "insurance_type": "{{insurance value}}", // from detail fetch API
    "amount": "1000",
    "debit_note_number": "11111",
    "customer_name": "customer_name",
    "customer_address": "Thimi",
    "mobile_number": "9851168561",
    "policy_description": "11111",
    "bill_no": "bill no",    // user input
    "email": "babubaiyaa@gmail.com",    // user input
    "token": "token",
    "reference": "Unique_identifier"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "detail": "Successful Payment",
    "message": "Successfully Completed Transaction",
    "credits_consumed": 1000.0,
    "credits_available": 92900.0,
    "extra_data": {},
    "id": null
}
</code></pre>
