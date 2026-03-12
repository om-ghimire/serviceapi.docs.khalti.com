# Synergy Service API Documentation

The **Synergy Service** allows you to fetch customer loan details and make payments for services such as **Batas Hire Purchase**. This documentation explains the API endpoints used to retrieve customer details and process payments.

---

## Details Fetch

**URL:** `{{base_url}}/api/servicegroup/details/synergy/`

**Method:** POST

### Request Parameters

The following parameters are required in the POST request:

- **reference:** Unique reference ID for the request
- **customer_code:** Customer identifier
- **service_slug:** Service identifier (example: `batas-hire-purchase`)
- **token:** Authentication token

### Request Example

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "b121a497-7d23-402e-8e63-fb1db009a26e",
    "customer_code": "0100610101",
    "service_slug": "batas-hire-purchase"
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "customer_code": "14.011.01.2",
    "customer_name": "KALPANA  KAUCHA",
    "customer_address": "Dhudhilabhati-4, Sanisaura, Baglung",
    "branch_name": "Branch Office Kathmandu",
    "center_code": "14.011",
    "accrued_upto": "2074/11/28",
    "saving_amount": 210,
    "loan_principle_amount": 10763,
    "loan_interest_amount": 3265,
    "loan_penalty_amount": 0,
    "accrued_amount": 14238,
    "requires_deposited_by": true,
    "session_id": 622,
    "status": true
}
</code></pre>

### Response Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| customer_code | string | Unique customer code |
| customer_name | string | Customer full name |
| customer_address | string | Customer address |
| branch_name | string | Branch handling the loan |
| center_code | string | Center code associated with the customer |
| accrued_upto | string | Date until which the loan is accrued |
| saving_amount | float | Customer saving amount |
| loan_principle_amount | float | Loan principal amount |
| loan_interest_amount | float | Total loan interest |
| loan_penalty_amount | float | Penalty amount if applicable |
| accrued_amount | float | Total accrued amount |
| requires_deposited_by | boolean | Indicates if depositor name is required |
| session_id | integer | Session identifier |
| status | boolean | Request status |

---

## Make Payment

**URL:** `{{base_url}}/api/servicegroup/commit/synergy/`

**Method:** POST

### Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token
- **reference:** Unique reference ID for the transaction
- **amount:** Payment amount
- **service_slug:** Service identifier (example: `batas-hire-purchase`)
- **session_id:** Session ID obtained from the details endpoint
- **deposited_by:** Name of the person making the deposit (required if `requires_deposited_by = true`)

### Request Example

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "f0f43365-b2a6-48de-a226-de686cb3cf5f",
    "amount": "10",
    "service_slug": "batas-hire-purchase",
    "session_id": "622",
    "deposited_by": "Test Shrestha"
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Deposited Successfully",
    "credits_consumed": 10,
    "credits_available": 99993007174.2798,
    "id": 166066
}
</code></pre>

### Response Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| status | boolean | Transaction status |
| state | string | Transaction state |
| message | string | Transaction message |
| extra_data | object | Additional transaction data |
| detail | string | Transaction detail |
| credits_consumed | float | Amount consumed in the transaction |
| credits_available | float | Remaining available credits |
| id | integer | Transaction ID |