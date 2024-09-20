# Himalayan General Insurance

## Overview

This document outlines the APIs for fetching user details and processing payments related to Himalayan General Insurance. 

### User Detail Fetch API

- **Request URL:** `{{base_url}}/api/servicegroup/details/hg-insurance/`
- **Request Method:** POST
- **Service Params:** N/A

#### Response Example:

<pre><code class="json">
{
    "insured_party": "Jeetendra Maharjan",
    "policy_no": "KTM/MCY/11/18/19/95868",
    "premium_amount": 4875.56,
    "expiry_date": "2019-05-24",
    "insured_amount": 200000,
    "coverage_type": "Comprehensive",
    "ids": "5cff2e048c36076fac6a4d0d",
    "session_id": 161,
    "status": true
}
</code></pre>

### Payment API

- **Request URL:** `{{base_url}}/api/servicegroup/commit/hg-insurance/`
- **Request Method:** POST
- **Service Params:**

<pre><code class="json">
{
    "token": "token",
    "session_id": 161,
    "reference": "reference123",
    "amount": 4875.56
}
</code></pre>

#### Response Example:

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "premium_amount": 4875.56,
        "policy_no": "KTM/MCY/11/18/19/95868",
        "coverage_type": "Comprehensive",
        "insured_amount": 200000
    },
    "detail": "Successful Payment",
    "credits_consumed": 4875.56,
    "credits_available": 96786310.1950002,
    "id": 5878
}
</code></pre>
