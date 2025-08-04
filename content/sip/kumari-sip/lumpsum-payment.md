# Kumari Capital SIP Lumpsum Purchase API

## Overview

This API allows a one-time **lumpsum investment** into the Kumari Capital SIP scheme.  
It supports both individual and institutional investors and requires valid DP and BOID info.

**URL:** [{{base_url}}/api/use/kumari-sip-lumpsum-purchase/](https://{{base_url}}/api/use/kumari-sip-lumpsum-purchase/)  
**Type:** Lumpsum Purchase API  
**Method:** POST

---

## Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token (required)
- **reference:** Unique transaction reference (GUID recommended)
- **amount:** Investment amount (required)
- **is_institution:** `"true"` or `"false"` depending on investor type
- **first_name, middle_name, last_name:** Name of the investor (required for individuals)
- **company_name:** Required if `is_institution` is `true`
- **email:** Email address of the investor (required)
- **mobile_number:** Valid mobile number (required)
- **dp_name:** Full DP name with code (as returned by info API)
- **client_id:** BOID of the investor (required)

---

## Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}",
  "amount": 1000,
  "is_institution": "True",
  "first_name": "Test",
  "last_name": "Test",
  "middle_name": "Kumari",
  "company_name": "Test",
  "email": "test@Test.com",
  "mobile_number": "9863630699",
  "dp_name": "SANIMA BANK LTD (13015800)",
  "client_id": "12456781"
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
  "detail": "Lumpsum investment created successfully",
  "credits_consumed": 1000.0,
  "credits_available": xxxx.xxx,
  "id": 166062
}
</code></pre>
