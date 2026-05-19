Insure Tech Life Insurance

This document provides the necessary information for interacting with the Insure Tech Insurance API, detailing the required parameters and expected responses for fetching user details.

Note: Below is the list of Insurance under Insure Tech and their service slugs:

- Sun Nepal Life Insurance: `sun-nepal-premium`

### Fetch User Details
**POST**  
`{{base_url}}/api/servicegroup/details/insurtech-premium/`

#### Request Body

<pre><code class="json">
{
    "token": "{{token}}",
    "request_id": "106000001049",
    "dob": "1972-11-30",
    "reference": "unique reference",
    "service": "service_slug"
}
</code></pre>

#### Response

<pre><code class="json">
{
    "session_id": 44992,
    "transaction_id": "REP20260518142454403",
    "response_message": "Success",
    "amount": 2418,
    "request_id": "103000003009-1993-11-06",
    "properties": {
        "policy_no": "103000003009",
        "customer_name": "Hom Bahadur Khadka",
        "address": "Koshi Province,Sunsari,Ramdhuni Municipality,7",
        "product_name": "Renewable Term Assurance",
        "premium": "2333",
        "due_date": "12/22/2025 00:00:00",
        "late_fee": "85",
        "waive_amount": "0.00",
        "previous_excess_short": "0.00"
    },
    "status": true
}
</code></pre>

---

## Make Payment
**POST**  
`{{base_url}}/api/servicegroup/commit/insurtech-premium/`

#### Request Body

<pre><code class="json">
{
    "token": "{{token}}",
    "session_id": "{{session_id}}",
    "service": "service_slug",
    "reference": "{{$guid}}",
    "amount": "{{amount}}"
}
</code></pre>

#### Response

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": {},
    "credits_consumed": 18692,
    "credits_available": 99989176227.8998,
    "id": 176682
}
</code></pre>