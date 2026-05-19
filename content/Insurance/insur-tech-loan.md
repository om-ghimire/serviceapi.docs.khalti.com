Insure Tech Loan Repayment

This document provides the necessary information for interacting with the Insure Tech Loan Repayment API, detailing the required parameters and expected responses for fetching user details.

Note: Below is the list of Insurance under Insure Tech and their service slugs:

- Sun Nepal Life Insurance: "sun-nepal-loan-repayment"

### Fetch User Details
**POST**  
`{{base_url}}/api/servicegroup/details/insurtech-loan-repayment/`

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
    "session_id": 44993,
    "transaction_id": "LRP20260518143252140",
    "response_message": "Success",
    "amount": 178520,
    "request_id": "101000000020-1975-07-30",
    "properties": {
        "policy_no": "101000000020",
        "customer_name": "Tara Kumari Lakandri",
        "product_name": "SunLife Endowment Plan",
        "interest_rate": "12.00",
        "interest": "28894.00",
        "loan_amount": "150000.00",
        "loan_Date": "2022-12-11",
        "principal_amount": "149626.00"
    },
    "status": true
}
</code></pre>

---

## Make Payment
**POST**  
`{{base_url}}/api/servicegroup/commit/insurtech-loan-repayment/`

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