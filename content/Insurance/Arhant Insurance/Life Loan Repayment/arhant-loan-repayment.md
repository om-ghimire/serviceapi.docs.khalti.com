# Arhant Life Insurance - Loan Repayment

## Overview

The **Arhant Life Insurance Loan Repayment API** allows users to fetch loan repayment details for life insurance policy-linked loans and process the repayment.  
This is a multi-step API 

**Supported service_slug for Loan Repayment:**

| Life Insurance              | service_slug                           |
|-----------------------------|----------------------------------------|
| IME Life Insurance          | `ime-life-insurance-loan-repayment`    |
| Prabhu Mahalaxmi Loan Repayment          | `prabhu-mahalaxmi-loan-repayment`    |

---

### 1. Detail Fetch API (Loan Repayment Details)

**Request URL:**  
`{{base_url}}/api/servicegroup/details/arhant-life-insurance-loan-repayment/`

**Request Method:** POST

**Request Payload:**

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "policy_no": "101000000009",
    "insurance_slug": "ime-life-insurance-loan-repayment"
}
</code></pre>

**Successful Response:**

<pre><code class="json">
{
    "request_id": "101000000009-1988",
    "amount": 81448.86,
    "properties": {
        "interest": "5448.86",
        "loan_Date": "2024-03-14",
        "policy_no": "101000000009",
        "loan_amount": "76000.00",
        "product_name": "Endowment Cum Whole Life Plan - Amulya",
        "customer_name": "Samjhana Basnet",
        "interest_rate": "10.50",
        "principal_amount": "76000.00"
    },
    "session_id": 46973,
    "status": true
}
</code></pre>

---

### 2. Payment / Commit API

**Request URL:**  
`{{base_url}}/api/servicegroup/commit/arhant-life-insurance/`

**Request Method:** POST

**Request Payload:**

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "session_id": 46973,
    "amount": "81448.86"
}
</code></pre>

**Successful Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": {
        "reference_code": "51080002489|30|RP050798000165",
        "amount": 2442,
        "message": "RP Paid Successfully",
        "request_id": "51080002489-2007"
    },
    "credits_consumed": 81448.86,
    "credits_available": 99988883605.7998,
    "id": 178648
}
</code></pre>


