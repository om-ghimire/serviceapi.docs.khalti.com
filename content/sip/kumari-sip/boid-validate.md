# Kumari Capital SIP Validation API

## Overview

This API validates whether a given **client ID** and **DP name** are eligible for SIP registration with Kumari Capital.  
It checks BOID validity, user status, active SIPs, DRIP status, and due installments.

**URL:** [{{base_url}}/api/servicegroup/validate/kumari-capital-sip/](https://{{base_url}}/api/servicegroup/validate/kumari-capital-sip/)  
**Type:** Validation API  
**Method:** POST

---

## Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token (required)
- **client_id:** BOID of the customer (required)
- **dp_name:** Full DP name as returned from the info API (required)

---

## Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "client_id": "12345678",
  "dp_name": "SANIMA BANK LTD (13015800)"
}
</code></pre>

---

## Success Response Format

<pre><code class="json">
{
  "details": {
    "is_user": false,
    "is_valid": true,
    "message": "Boid is valid",
    "has_active_sip": false,
    "is_drip_enabled": true,
    "has_due_installment": false
  },
  "status": true
}
</code></pre>
