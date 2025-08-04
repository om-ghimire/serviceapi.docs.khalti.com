# CDSC Details API

## Overview

This API provides **renewal details** for Meroshare and Demat services for a given client code and selected DP.  
It returns expiry dates, pricing, allowed duration, and consumer identification information.

**URL:** [{{base_url}}/api/servicegroup/details/cdsc/](https://{{base_url}}/api/servicegroup/details/cdsc/)  
**Type:** Details API  
**Method:** POST

---

## Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token (required)
- **reference:** Unique transaction reference (required)
- **client_code:** BOID or Client ID (required)
- **payment_type:** Type of service to renew (`"Meroshare"`, `"Demat"` or `"Both"`)
- **service_slug:** DP slug from the `/info/cdsc/` API (required)

---

## Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}",
  "client_code": "00063951",
  "payment_type": "Both",
  "service_slug": "nic-asia-bank-limited-13700"
}
</code></pre>

---

## Success Response Format

<pre><code class="json">
{
  "consumer_name": "BAL SHANKER THAPA RESHMI",
  "dp_name": "NIBL ACE CAPITAL LIMITED",
  "meroshare_renew": {
    "amount": 5,
    "max_year": 5,
    "min_year": 1,
    "expiry_date": "Jan 6, 2054 3:35:24 PM"
  },
  "demat_renew": {
    "amount": 10,
    "max_year": 20,
    "min_year": 1,
    "expiry_date": "2093-03-31"
  },
  "session_id": 9075,
  "status": true
}
</code></pre>
