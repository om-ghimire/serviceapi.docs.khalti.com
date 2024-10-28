# Rastriya Beema Sansthan

**Type: Multi-Step API**

## 1. Detail Fetch

**Request URL:** `{{base_url}}/api/servicegroup/details/rastriya-beema-sasthan/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "reference": "unique_identifier",
  "token": "token",
  "policy_no": "49726",
  "dob": "1962-08-10"
}
</code></pre>

**Request Example:**

<pre><code class="json">
{
  "reference": "unique_ref_123",
  "token": "your_token_here",
  "policy_no": "49726",
  "dob": "1962-08-10"
}
</code></pre>

**Response:**

<pre><code class="json">
{
  "premium_amount": 8392.0,
  "customer_name": "NAVA NIDHI PANT",
  "address": "ILIT ENGLISH SCHOOL BUTWAL",
  "total_amount": 100.0,
  "policy_no": "49726",
  "product_name": "Endowment",
  "fine_amount": 80,
  "next_due_date": "1999-07-19",
  "current_due_date": "1999-07-19",
  "pay_mode": "Yearly",
  "session_id": 1913,
  "status": true
}
</code></pre>

## 2. Payment API

**Request URL:** `{{base_url}}/api/servicegroup/commit/rastriya-beema-sasthan/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "token",
  "session_id": "{{session_id}}",   // From Detail Fetch API
  "amount": "{{total_amount}}"       // From Detail Fetch API
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
  "credits_available": 92720.0,
  "id": 105658
}
</code></pre>
