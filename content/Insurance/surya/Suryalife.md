# 11.5 Surya Jyoti Life Insurance API

**Note**: Jyoti and Surya Life Insurance have merged. Please use the Surya Life Insurance API.

## Overview

The Surya Jyoti Life Insurance API provides functionalities for retrieving policy details and processing payments for Surya Life Insurance policies. The API involves two main operations:

1. **Detail Fetch API**: Retrieves detailed information about an insurance policy using the policy number and date of birth.
   
2. **Payment API**: Processes payments for the insurance policy using the information retrieved from the Detail Fetch API.

## Surya Jyoti Life Detail Fetch API

**Request URL**: {{base_url}}/api/servicegroup/details/surya-life-insurance/

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
    "token": "<token>",
    "policy_no": "7000000019",
    "dob": "1988-02-21",
    "reference": "<unique reference id>"
}
</code></pre>

**Success Response**:

<pre><code class="json">
{
    "policy_no": "207001096",
    "plan_code": "71",
    "pay_mode": "YRLY",
    "name": "Ram Thakur",
    "premium_amount": 10211,
    "fine_amount": 85,
    "adjustment_amount": 0,
    "amount": "10296",
    "payment_date": "06/07/2023",
    "due_date": "20/05/2023",
    "next_due_date": "20/05/2024",
    "policy_status": "ACTIVE",
    "term": "15",
    "maturity_date": "20/05/2025",
    "session_id": 9470,
    "status": true
}
</code></pre>

**Error Response**:

<pre><code class="json">
{
    "status": false,
    "error_code": "4000",
    "message": "Can't fulfill request",
    "error": "client_error",
    "details": "Invalid Date of Birth/Policy Number",
    "error_data": {},
    "state": "Error"
}
</code></pre>

**Overview**: 
The Detail Fetch API retrieves comprehensive details about a specific insurance policy based on the policy number and date of birth. It provides information such as the policy number, premium amount, fine amount, due dates, and policy status.

## Surya Jyoti Life Payment API

**Request URL**: {{base_url}}/api/servicegroup/commit/surya-life-insurance/

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
    "token": "<token>",
    "session_id": "<session id from detail step>",
    "reference": "reference123",
    "amount": 1305
}
</code></pre>

**Success Response**:

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "customer_name": "Parbati Kunwar Karki",
        "fine_amount": 0.0,
        "adjustment_amount": 0.0,
        "premium_amount": 8430.0,
        "payment_date": "02/06/2020",
        "next_due_date": "20/05/2021",
        "policy_no": "111001524",
        "total_amount": 8430.0
    },
    "detail": "Transaction Successful",
    "credits_consumed": 8430.0,
    "credits_available": 477719.77,
    "id": 85407
}
</code></pre>

**Error Response**:

<pre><code class="json">
{
    "status": false,
    "error_code": "1011",
    "message": "Validation error",
    "error": "validation_error",
    "details": {
        "amount": "Invalid Amount"
    },
    "error_data": {
        "amount": "Invalid Amount"
    },
    "state": "Error"
}
</code></pre>

**Overview**: 
The Payment API processes payments for a Surya Life Insurance policy. It requires details such as the session ID (from the Detail Fetch API), payment amount, and a unique reference identifier. On successful completion, it returns transaction details including customer name, payment date, and total amount. If there are issues, such as invalid payment amounts, the API will return an error response with relevant details.
