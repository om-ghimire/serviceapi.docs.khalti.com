# CDSC Info API

## Overview

This API provides a list of available **DPs (Depository Participants)** and supported **payment types**.  
It is typically used to populate selection options before initiating a transaction.

**URL:** [{{base_url}}/api/servicegroup/info/cdsc/](https://{{base_url}}/api/servicegroup/info/cdsc/)  
**Type:** Info API  
**Method:** POST

---

## Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token (required)
- **reference:** Unique reference ID (GUID format recommended)

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
  "dp_list": [
    {
      "name": "Global Ime Capital Limited (11200)",
      "slug": "global-ime-capital-limited-11200"
    },
    {
      "name": "Magnet Securities and Investment Company (22200)",
      "slug": "magnet-securities-and-investment-company-22200"
    },
    {
      "name": "Nic Asia Bank Limited (13700)",
      "slug": "nic-asia-bank-limited-13700"
    },
    {
      "name": "Sanima Bank Ltd (15800)",
      "slug": "sanima-bank-ltd-15800"
    },
    {
      "name": "Sumeru  Securities  Private  Limited (14200)",
      "slug": "sumeru-securities-private-limited-14200"
    }
  ],
  "payment_types": [
    "Meroshare",
    "Demat",
    "Both"
  ]
}
</code></pre>
