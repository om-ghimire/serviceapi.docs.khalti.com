# Kumari Capital SIP API

## Overview

The Kumari Capital SIP API allows clients to fetch available DP providers, interval options, and mode options for setting up a SIP (Systematic Investment Plan).  
This API requires a `POST` request with an authentication token and a unique reference identifier.

**URL:** [{{base_url}}/api/servicegroup/info/kumari-capital-sip/](https://{{base_url}}/api/servicegroup/info/kumari-capital-sip/)  
**Type:** Info API  
**Method:** POST

---

## Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token (required)
- **reference:** Unique reference identifier

---

## Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}"
}
</code></pre>

---

## Success Response Format

<pre><code class="json">
{
  "dps": [
    "SANIMA BANK LTD (13015800)",
    "NEPAL DP LIMITED (13015500)",
    "EVEREST BANK LTD. (13010800)",
    "NABIL BANK LIMITED (13015100)",
    "NABIL BANK LIMITED (13016800)",
    "NEPAL BANK LIMITED (13015700)",
    "SAJILO BROKER LTD. (13021700)",
    "KUMARI BANK LIMITED (13015200)",
    "KUMARI BANK LIMITED (13016300)",
    "NMB CAPITAL LIMITED (13011000)",
    "PRABHU BANK LIMITED (13013900)",
    "PRABHU BANK LIMITED (13016000)",
    "CAPITAL HUB PVT. LTD (13020900)",
    "ICFC FINANCE LIMITED (13017400)"
  ],
  "interval_options": [
    "monthly",
    "quarterly",
    "yearly",
    "half-yearly"
  ],
  "mode_options": [
    "limited",
    "unlimited"
  ]
}
</code></pre>
