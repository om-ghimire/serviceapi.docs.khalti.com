# Arhant Life Insurance

## Overview

The Arhant Life Insurance API allows users to fetch details about their life insurance policies and process payments. This multi-step API supports various life insurance products under Arhant, including Asian Life Insurance and Ime Life Insurance.

### **Type: Multi Step API**

**Below is the list of Life Insurances under Arhant and their service_slug:**

1. ##### **Asian Life Insurance : asian-life-insurance**
2. ##### **Ime Life Insurance : ime-life-insurance**

---

### 1. **Detail Fetch API**

**Request URL:** `{{url}}/api/servicegroup/details/arhant-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "policy_no": "51080000258",    // User input
    "dob_year": "1984",            // User input
    "insurance_slug": "service_slug",
    "reference": "unique-reference"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "request_id": "51080000258-1984",
    "amount": 4803,
    "properties": {
        "policy_no": "51080000258",
        "customer_name": "Chandra Kala Ghimire",
        "address": "Fidim-4",
        "product_name": "Endowment",
        "premium": "4803",
        "late_fee": "0",
        "waive_amount": "0",
        "previous_excess_short": "0.00"
    },
    "session_id": 8867,
    "status": true
}
</code></pre>

---

### 2. **Payment API**

**Request URL:** `{{base_url}}/api/servicegroup/commit/arhant-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "session_id": "137",
    "amount": "amount"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Success",
    "credits_consumed": 4803,
    "credits_available": 999999998060930.6,
    "id": 62849
}
</code></pre>
