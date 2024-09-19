# Surya Life Insurance First Payment

## Overview

The Surya Life Insurance API facilitates the first payment process for policyholders. It includes a detail retrieval step that provides essential information about the policy, followed by a payment submission step.

### **Type: Multi Step API**

---

### 1. **Detail API**

**Request URL:** `{{base_url}}/api/servicegroup/first_payment/surya-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "policy_no": "132468",
    "reference": "Unique_Reference",
    "service_slug": "surya-life-first-payment"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "customer_name": "Suresh Raj Joshi",
    "address": "Sabhapokhari",
    "plan_name": "Surya Surachhit (Limited Payment)",
    "policy_no": "77777780079",
    "sum_assured": 100000,
    "premium_amount": 40,
    "payment_date": "31/05/2021",
    "term_year": "1",
    "pay_mode": "SNGL",
    "amount": "40",
    "session_id": 286,
    "status": true
}
</code></pre>

---

### 2. **Payment API**

**Request URL:** `{{base_url}}/api/servicegroup/commit/surya-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "session_id": "286",                      // Obtained from detail API
    "reference": "Unique Identifier",
    "service_slug": "surya-life-first-payment",
    "amount": "40"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "customer_name": "Suresh Raj Joshi",
        "fine_amount": 0.0,
        "adjustment_amount": 0.0,
        "premium_amount": 40.0,
        "payment_date": "31/05/2021",
        "next_due_date": "",
        "policy_no": "77777780079",
        "total_amount": 40.0
    },
    "detail": "Transaction Successful",
    "credits_consumed": 40.0,
    "credits_available": 9999625028.47,
    "id": 34864
}
</code></pre>
