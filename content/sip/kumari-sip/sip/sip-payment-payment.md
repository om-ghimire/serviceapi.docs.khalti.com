# Kumari Capital SIP Commit Payment API

## Overview

This API is used to **finalize and commit a SIP payment** based on a previously retrieved payment schedule.  
It consumes credits and confirms the payment by session ID and amount.

**URL:** [{{base_url}}/api/servicegroup/commit/kumari-capital-sip/](https://{{base_url}}/api/servicegroup/commit/kumari-capital-sip/)  
**Type:** Commit Payment API  
**Method:** POST

---

## Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token (required)
- **session_id:** Session ID from the `/details/kumari-capital-sip/` API
- **no_of_installments:** Number of installments to pay (e.g., `3`)
- **amount:** Total amount to be committed (e.g., `5000.00 * no_of_installments`)

---

## Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": 41403,
  "no_of_installments": 3,
  "amount": 15000.00
}
</code></pre>

---

## Success Response Format

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {},
  "detail": "Payment completed successfully!",
  "extra_info": {
    "payment_code": "ZAY7I4C2TP"
  },
  "credits_consumed": 1000,
  "credits_available": 999079050,
  "id": 130028
}
</code></pre>
