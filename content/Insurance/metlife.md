# MetLife API

## Overview

The MetLife API provides insurance policy details and enables payment for premiums. It requires POST requests with authentication tokens.

---

## Get Policy Details

**URL:** `{{base_url}}/api/servicegroup/details/metlife/`  
**Method:** POST

### Request Parameters

- **token:** Authentication token  
- **reference:** Unique transaction reference  
- **policy_no:** Insurance policy number  
- **birth_year:** Birth year of the insured person

### Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}",
  "policy_no": "n9251935",
  "birth_year": 1987
}
</code></pre>

### Success Response Format

<pre><code class="json">
{
  "ref_code": "37991818D648B4811",
  "policy_num": "379918",
  "mode": "MONTHLY",
  "insured_name": "RAYAMAJHI, JHABINDRA",
  "owner_name": "RAYAMAJHI, JHABINDRA",
  "amount": 3838,
  "agent_code": "060099000",
  "due_date": "24-Jan-2024",
  "next_due_date": "",
  "maturity_date": "24-Dec-2046",
  "contact_number": "9867803515",
  "address": "TOKHA MILAN CHOK-6,",
  "session_id": 41411,
  "status": true
}
</code></pre>

---

## Make Payment

**URL:** `{{base_url}}/api/servicegroup/commit/metlife/`  
**Method:** POST

### Request Parameters

- **token:** Authentication token  
- **session_id:** Session ID from the policy details response

### Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": 41411
}
</code></pre>

### Success Response Format

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {
    "email": "JHABBI1991@GMAIL.COM",
    "due_date": "24-Jan-2024",
    "payment": "3838",
    "ref_code": "37991818D648AC80B",
    "pol_number": "379918",
    "status_msg": "SUCCESS",
    "status_code": "00",
    "created_date": "01-Feb-2024",
    "created_time": "17:45:33",
    "next_due_date": "24-Feb-2024",
    "payment_type": "PREMIUM",
    "updated_date": "01-Feb-2024",
    "updated_time": "17:46:20",
    "payment_gateway": "KHALTI"
  },
  "detail": "SUCCESS",
  "credits_consumed": 3838.0,
  "credits_available": xxxxx.xxx,
  "id": 166088
}
</code></pre>
