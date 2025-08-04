# Kumari Capital SIP Registration API

## Overview

This API registers a SIP (Systematic Investment Plan) for a given BOID and DP.  
It supports both individual and institutional registrations with optional DRIP, and allows control over interval, mode, and duration.

**URL:** [{{base_url}}/api/use/kumari-sip-registration/](https://{{base_url}}/api/use/kumari-sip-registration/)  
**Type:** Action API  
**Method:** POST

---

## Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token (required)
- **reference:** Unique transaction reference (required)
- **amount:** Investment amount (required, e.g., 1000)
- **is_institution:** `true` or `false` to specify type of user
- **first_name, middle_name, last_name:** Full name (required for individuals)
- **company_name:** Name of institution (required if `is_institution` is `true`)
- **email:** Email address of user (required)
- **mobile_number:** Mobile number of user (required)
- **interval:** SIP interval (e.g., `"monthly"`, `"quarterly"`, `"yearly"`, `"half-yearly"`)
- **mode:** SIP mode (`"limited"` or `"unlimited"`)
- **period:** Number of periods if `mode` is `"limited"` (e.g., 2)
- **dp_name:** DP name as returned from the info API
- **client_id:** BOID of the investor
- **enable_drip:** Optional flag to enable dividend reinvestment (DRIP)

---

## Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}",
  "amount": 1000,
  "is_institution": false,
  "first_name": "test",
  "last_name": "test",
  "middle_name": "Kumari",
  "email": "test.test@khalti.com",
  "mobile_number": "9863630689",
  "interval": "quarterly",
  "mode": "limited",
  "period": 2,
  "dp_name": "SANIMA BANK LTD (13015800)",
  "client_id": "02325342"
  "company_name": "Test Company", 
  "enable_drip":true, 
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
  "detail": "SIP Registered successfully",
  "credits_consumed": 1000.0,
  "credits_available": xxxxx.xxx,
  "id": 166054
}
</code></pre>
