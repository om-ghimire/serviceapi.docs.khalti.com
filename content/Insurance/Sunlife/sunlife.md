# **Sun Life Insurance**

**Type**: Multi Step API

## 1. Detail Fetch

**Request URL**: [{{base_url}}/api/servicegroup/details/sun-life-insurance/](http://api/servicegroup/details/sun-life-insurance/)

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
  "reference": "<unique_identifier>",
  "token": "<token>",
  "policy_no": "66160014378",
  "dob": "1968-06-01"
}
</code></pre>

**Response**:

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
    "current_due_date": "2020-04-24",
    "pay_mode": "Yearly",
    "session_id": 1916,
    "status": true
}
</code></pre>

## 2. Payment API

**Request URL**: [{{base_url}}/api/servicegroup/commit/sun-life-insurance/](http://api/servicegroup/commit/sun-life-insurance/)

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
  "token": "<token>",
  "session_id": "{{session_id}}",   // From Detail Fetch API
  "amount": "{{total_amount}}",     // From Detail Fetch API
  "reference": "<unique_identifier>"
}
</code></pre>

**Response**:

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
    "credits_available": 75322.0,
    "id": 105695
}
</code></pre>
