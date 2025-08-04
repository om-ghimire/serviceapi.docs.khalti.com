# CDSC Commit API

## Overview

This API **confirms and completes** the renewal transaction for Meroshare and/or Demat services, based on details received from the `/details/cdsc/` API.  
It requires a valid session ID and renewal year inputs and deducts credits upon successful renewal.

**URL:** [{{base_url}}/api/servicegroup/commit/cdsc/](https://{{base_url}}/api/servicegroup/commit/cdsc/)  
**Type:** Commit API  
**Method:** POST

---

## Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token (required)
- **session_id:** Session ID from the `/details/cdsc/` API
- **meroshare_renew_year:** Number of years to renew Meroshare (optional if `payment_type` is not Meroshare)
- **demat_renew_year:** Number of years to renew Demat (optional if `payment_type` is not Demat)
- **amount:** Total amount for the renewal (calculated from details API)
- **reference:** Unique reference ID

---

## Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": {{session_id}},
  "meroshare_renew_year": 1,
  "demat_renew_year": 3,
  "amount": 35,
  "reference": "{{$guid}}"
}
</code></pre>

---

## Success Response Format

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {
    "consumer_name": "xxx x xx xx",
    "renewed_date": "Aug 9, 2025 3:23:11 PM",
    "meroshare_expiry_date": "Jan 3, 2062 3:35:24 PM",
    "demat_expiry_date": ""
  },
  "detail": "Account Renewal  Successful",
  "credits_consumed": 25,
  "credits_available": xxxxxxx,
  "id": 85077
}
</code></pre>
