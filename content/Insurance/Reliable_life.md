# Reliable Life Insurance

## Overview

The Reliable Life Insurance API facilitates a multi-step process for fetching policy details and processing payments. It enables users to retrieve information about their insurance policies and make payments for premiums.

## **Type: Multi Step API**

### 1. **Detail Fetch**

**Request URL:** `{{base_url}}/api/servicegroup/details/reliable-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "reference": "Unique_Identifier",
    "policy_no": "101000000008",
    "dob": "2018-09-26"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "premium_amount": 100.0,
    "customer_name": "test test1",
    "address": "Malakheti",
    "total_amount": 180.0,
    "policy_no": "701000000052",
    "product_name": "Endowment Cum Whole Life Plan - Amulya",
    "fine_amount": 80.0,
    "next_due_date": "2020-04-24",
    "pay_mode": "Yearly",
    "session_id": 1013,
    "status": true
}
</code></pre>

---

### 2. **Payment API**

**Request URL:** `{{base_url}}/api/servicegroup/commit/reliable-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "reference": "Unique_identifier",
    "token": "token",
    "session_id": "1013",
    "amount": "180"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "id": 70282,
    "status": true,
    "state": "Queued",
    "detail": "Transaction Queued",
    "message": "Your operation is in queue.",
    "credits_consumed": 180.0,
    "credits_available": 742509.83,
    "extra_data": {}
}
</code></pre>
