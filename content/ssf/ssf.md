# Social Security Fund API

## Overview

The SSF API provides endpoints for checking details and making payments to the Social Security Fund. The API requires POST requests and provides information about the success or failure of the transactions.

## Details Endpoint

**URL:** `{{base_url}}/api/servicegroup/details/social-security-fund/`
**Method:** POST

### Request Parameters

The following parameters are required in the POST request:

- **token:**  Proivded token
- **submission_no:** Submission number
- **reference:** Unique reference for the transaction
- **emp_id:** Employee ID

### Request Example

<pre><code class="json">
{
"token":"{{token}}"
"submission_no":"20800002718860",
"reference":"{{reference}}",
"emp_id":"20801305249"
}
</code></pre>

### Success Response Format
<pre><code class="json">
{
    "submission_no": "20760000077860",
    "emp_id": "330704J1130004604",
    "emp_name_nep": "अमरज्योति बचत तथा ऋण सहकारी संस्था लिमिटेड ",
    "emp_name_eng": "Amarjyoti Saving & Credit Co-operative Limited",
    "year": 2076,
    "month": 7,
    "email": "test50841602@test.com",
    "phone": "",
    "amount": 18872.8,
    "session_id": 105,
    "status": true
}
</code></pre>

## Payment Endpoint

**URL:** `{{base_url}}/api/servicegroup/commit/social-security-fund/`
**Method:** POST

### Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token
- **amount:** Payment amount
- **session_id:** Session ID received from details endpoint

### Request Example

<pre><code class="json">
"amount":"{{amount}}", // obtain from details fetch api 
"token":{{token}},  // obtain from details fetch api 
"session_id":"{{session_id}}"// obtain from details fetch api 

</code></pre>

### Success Response Format
<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "voucher_no": "SP821000000004",
        "submission_no": "20800002718860"
    },
    "detail": "Successfully Done!",
    "credits_consumed": 18872.8,
    "credits_available": xxxx,
    "id": xxxx
}
</code></pre>

