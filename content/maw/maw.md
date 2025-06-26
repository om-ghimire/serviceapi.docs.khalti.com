# MAW EMI Service API Documentation


 The MAW EMI Service allows you to fetch EMI loan details and make payments for loans associated with mobile phones. This documentation explains the API endpoints used to retrieve loan details and process payments



##  Details Fetch 



**URL:** `{{base_url}}/api/servicegroup/details/maw-emi/`

**Method:** POST

### Request Parameters

The following parameters are required in the POST request:

- **reference:** Unique reference ID for the request
- **client_code:** Client code for the merchant
- **service_slug:** Service identifier (maw)
- **token:** Authentication token

### Request Example

<pre><code class="json">
{
    "reference": "621dc9ae-66a4-426c-a5be-847c5fb7346c",
    "client_code": "00025001",
    "service_slug": "maw",
    "token": "OJqV4RQyx7ceCmqi69ae"
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "name": "SAJINDRA RAI",
    "client_code": "00037782",
    "loan_details": [
        {
            "due_days": 8,
            "nominee": "00100100037782000001",
            "main_code": "00102H00037782000002",
            "close_amount": 18599.4,
            "next_emi_date": "2025-06-20",
            "vehicle_type": "Mobile Phones",
            "interest_rate": 0.0,
            "total_overdue": 2066.6,
            "vehicle_model": "Redmi Note 14 5G 8+256",
            "next_emi_amount": 2066.6,
            "loan_account_balance": 0.0,
            "total_loan_outstanding": 18599.4,
            "remaining_installments": 8,
            "remaining_exluding_overdue": 0.0
        }
    ],
    "mobile_number": "9742537170",
    "session_id": 39014,
    "status": true
}
</code></pre>

### Response Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| name | string | Customer"s full name |
| client_code | string | Client code |
| loan_details | array | Array of loan details |
| mobile_number | string | Customer"s mobile number |
| session_id | integer | Session identifier |
| status | boolean | Request status |

#### Loan Details Object

| Parameter | Type | Description |
|-----------|------|-------------|
| due_days | integer | Number of days until next payment is due |
| nominee | string | Nominee identifier |
| main_code | string | Main loan account code |
| close_amount | float | Total amount to close the loan |
| next_emi_date | string | Date of next EMI payment |
| vehicle_type | string | Type of financed vehicle |
| interest_rate | float | Interest rate on the loan |
| total_overdue | float | Total overdue amount |
| vehicle_model | string | Model of the financed vehicle |
| next_emi_amount | float | Amount of next EMI payment |
| loan_account_balance | float | Current loan account balance |
| total_loan_outstanding | float | Total outstanding loan amount |
| remaining_installments | integer | Number of remaining installments |
| remaining_exluding_overdue | float | Remaining amount excluding overdue |

## Make Payment

**URL:** `{{base_url}}/api/servicegroup/commit/maw-emi/`
**Method:** POST


### Request Example

<pre><code class="json">
    {
    "token"="{{token}}",
    "session_id"="{{session_id}}",
    "vehicle"="{{vehicle}}",
    "amount"="{{amount}}"
    }
</code></pre>
### Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token (obtained from details endpoint)
- **session_id:** Session ID (obtained from details endpoint)
- **vehicle:** Vehicle code (obtained from loan_details.main_code)
- **amount:** Payment amount (obtained from loan_details.next_emi_amount)


### Response Example

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Success",
    "credits_consumed": xxx.x,
    "credits_available": xxxx.xx,
    "id": 161227
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
| id | integer | Transaction ID | # MAW EMI Service


