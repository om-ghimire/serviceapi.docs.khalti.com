# Prabhu Life Insurance

## Overview

The Prabhu Life Insurance API allows users to fetch policy details and process payments efficiently through a multi-step process.

### **Type: Multi Step API**

---

### 1. **Detail Fetch API**

**Request URL:** `{{base_url}}/api/servicegroup/details/prabhu-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "policy_no": "701000000052",
    "dob": "1996-12-11",
    "reference": "Unique Reference"
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
    "session_id": 320,
    "status": true
}
</code></pre>

---

### 2. **Payment API**

**Request URL:** `{{base_url}}/api/servicegroup/commit/prabhu-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "session_id": "320",  // session id received from detail fetch API
    "amount": "amount",
    "reference": "Unique Reference"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "assured_name": "test test1",
        "fine_amount": 80.0,
        "premium_amount": 100.0,
        "next_due_date": "2021-04-24",
        "policy_no": "701000000052",
        "total_amount": 180.0,
        "invoice_number": "RP30137"
    },
    "detail": "Successful Payment",
    "credits_consumed": 180.0,
    "credits_available": 9999633558.47,
    "id": 34846
}
</code></pre>
