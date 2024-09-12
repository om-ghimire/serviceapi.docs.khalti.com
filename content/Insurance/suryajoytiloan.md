# Surya Jyoti Loan Repayment

**Type: Multi-Step API**

## 1. Detail Fetch

**Request URL:** `{{base_url}}/api/servicegroup/details/surya-jyoti-loan-repayment/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "reference": "unique_identifier",
  "token": "token",
  "policy_no": "49726",
  "dob": "1962-08-10",
  "date_format": "AD / BS"
}
</code></pre>

**Request Example:**

<pre><code class="json">
{
  "reference": "unique_ref_123",
  "token": "your_token_here",
  "policy_no": "49726",
  "dob": "1962-08-10",
  "date_format": "AD"
}
</code></pre>

**Response:**

<pre><code class="json">
{
  "policy_no": "7330000152",
  "name": "Melina Magar",
  "policy_type": "Loan Repayment",
  "total_payable_amount": 18056.0,
  "minimum_payable": 10.0,
  "int_to_pay": 5.0,
  "loan_amount": 22000,
  "interest_calculated_from": "20/07/2022",
  "interest_calculated_to": "22/07/2022",
  "total_due_interest": 10.0,
  "principal_amount": 18051.0,
  "session_id": 17118,
  "status": true
}
</code></pre>

## 2. Payment API

**Request URL:** `{{base_url}}/api/servicegroup/commit/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "token",
  "session_id": "{{session_id}}",  // From Detail Fetch API
  "amount": "{{total_amount}}",    // From Detail Fetch API
  "reference": "unique_identifier"
}
</code></pre>

**Request Example:**

<pre><code class="json">
{
  "token": "your_token_here",
  "session_id": "17118",
  "amount": "18056.0",
  "reference": "unique_ref_123"
}
</code></pre>

**Response:**

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {
    "policy_no": "7330000152"
  },
  "detail": "Transaction Successful",
  "credits_consumed": 18056.0,
  "credits_available": 75502.0,
  "id": 105663
}
</code></pre>
