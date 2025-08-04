# Kumari Capital SIP Payment Details API

## Overview

This API provides **upcoming SIP payment schedules** for a given client and DP.  
It returns a list of scheduled installments along with due dates and SIP references.

**URL:** [{{base_url}}/api/servicegroup/details/kumari-capital-sip/](https://{{base_url}}/api/servicegroup/details/kumari-capital-sip/)  
**Type:** Payment Schedule Info API  
**Method:** POST

---

## Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token (required)
- **reference:** Unique request reference
- **dp_name:** Full DP name with code (required)
- **client_id:** BOID of the customer (required)
- **service_slug:** `"kumari-sip-payment"`

---

## Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}",
  "dp_name": "SANIMA BANK LTD (13015800)",
  "client_id": "12345666",
  "service_slug": "kumari-sip-payment"
}
</code></pre>

---

## Success Response Format

<pre><code class="json">
{
  "payment_schedules": [
    {
      "amount": "5000.00",
      "scheme_name": "Test open end scheme ",
      "interval_type": "monthly",
      "payment_due_date": "2024-09-28",
      "sip_reference_id": "SIP00000105",
      "installment_number": 2
    },
    {
      "amount": "5000.00",
      "scheme_name": "Test open end scheme ",
      "interval_type": "monthly",
      "payment_due_date": "2024-10-28",
      "sip_reference_id": "SIP00000105",
      "installment_number": 3
    },
    {
      "amount": "5000.00",
      "scheme_name": "Test open end scheme ",
      "interval_type": "monthly",
      "payment_due_date": "2024-11-28",
      "sip_reference_id": "SIP00000105",
      "installment_number": 4
    }
  ],
  "session_id": 41402,
  "status": true
}
</code></pre>
