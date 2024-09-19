# Citizen Life Insurance

## Overview

The Citizen Life Insurance API allows users to retrieve details about their insurance policies and process payments. This multi-step API provides access to policy information and facilitates secure transactions for premium payments.

## **Type: Multi Step API**

### 1. **Detail Fetch**

**Request URL:** `{{base_url}}/api/servicegroup/details/citizen-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "reference": "Unique_Identifier",
    "policy_no": "101000315",
    "dob": "1976-09-22"
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
    "session_id": 994,
    "status": true
}
</code></pre>

---

### 2. **Payment API**

**Request URL:** `{{base_url}}/api/servicegroup/commit/citizen-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "reference": "Unique_identifier",
    "token": "token",
    "session_id": "994",
    "amount": "180"
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
    "credits_available": 9995400876.57663,
    "id": 68751
}
</code></pre>
