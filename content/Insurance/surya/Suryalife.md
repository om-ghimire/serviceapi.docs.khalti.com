# Surya Jyoti Life Insurance Service API Documentation

The **Surya Jyoti Life Insurance Service** allows you to fetch policy details and make premium payments for life insurance policies. This documentation explains the API endpoints for retrieving policy details and processing payments.

---

## Details Fetch

  
**URL:** `{{base_url}}/api/servicegroup/details/surya-life-insurance/`  

**Method:** POST

### Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token  
- **reference:** Unique reference ID for the request  
- **dob:** Date of birth of the policyholder (`YYYY-MM-DD`)  
- **date_type:** Type of date (`AD` or `BS`)  
- **policy_number:** Policy number  
- **service_slug:** Service identifier (`surya-life-insurance` for staging, `surya-jyoti-life-insurance` for live)  

### Request Example

<pre><code class="json">
{
    "reference": "d5b8e6b5-ac8c-4475-90b3-103a57d3ae7c",
    "dob": "2014-08-09",
    "date_type": "AD",
    "policy_number": "405003539",
    "token": "{{token}}",
    "service_slug": "surya-life-insurance"
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "details": [
        {
            "policynumber": "20800000083",
            "assuredname": "Rita Sene (Khapung)",
            "gender": "FEMALE",
            "plancode": "151",
            "plan": "SuryaJyoti Sawadhik Jeevan Beema",
            "dobassured": "1990-10-02T00:00:00",
            "sumassured": 300000,
            "periodicpremium": 21515,
            "premiumtermyear": 15,
            "policytermyear": 15,
            "maturedate": "2038-09-17T00:00:00",
            "paymode": "YRLY",
            "mobile": "9860946708",
            "docdate": "2023-09-17T00:00:00",
            "recpayable": 0,
            "anticipateadjamount": 0,
            "fromduedate": "2025-09-17T00:00:00",
            "uptoduedate": "2025-09-17T00:00:00",
            "totalinterest": 0,
            "totalpremium": 21515,
            "totaldue": 21515,
            "dueinstallment": 1,
            "lastpremiumpaydate": "2037-09-17T00:00:00",
            "totaldueafteradjrecpay": 21515
        }
    ],
    "session": 41550,
    "status": true
}
</code></pre>

### Response Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| details | array | Array of policy details |
| details.policynumber | string | Policy number |
| details.assuredname | string | Policyholder name |
| details.gender | string | Gender of policyholder |
| details.plancode | string | Plan code |
| details.plan | string | Plan name |
| details.dobassured | string | Date of birth of the assured |
| details.sumassured | float | Sum assured |
| details.periodicpremium | float | Periodic premium amount |
| details.premiumtermyear | integer | Premium term in years |
| details.policytermyear | integer | Policy term in years |
| details.maturedate | string | Policy maturity date |
| details.paymode | string | Payment mode (e.g., YRLY) |
| details.mobile | string | Mobile number |
| details.docdate | string | Date of document creation |
| details.recpayable | float | Receivable amount |
| details.anticipateadjamount | float | Anticipated adjustment amount |
| details.fromduedate | string | From due date |
| details.uptoduedate | string | Up to due date |
| details.totalinterest | float | Total interest amount |
| details.totalpremium | float | Total premium amount |
| details.totaldue | float | Total due amount |
| details.dueinstallment | integer | Current installment number |
| details.lastpremiumpaydate | string | Last premium payment date |
| details.totaldueafteradjrecpay | float | Total due after adjustment |
| session | integer | Session ID for payment |
| status | boolean | Request status |

---

## Make Payment


**URL:** `{{base_url}}/api/servicegroup/commit/surya-life-insurance/`  

**Method:** POST

### Request Parameters

- **token:** Authentication token  
- **session_id:** Session ID obtained from details endpoint  
- **name:** Name of the person making the payment  
- **email:** Email of the payer  
- **mobile:** Mobile number of the payer  
- **anticipate_adj:** Optional, indicate anticipated adjustment (`1` for yes)  

### Request Example

<pre><code class="json">
{
    "session_id": "41550",
    "token": "{{token}}",
    "name": "test Shrestha",
    "email": "test@gmail.com",
    "mobile": "9801856451",
    "anticipate_adj": "1"
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "receipt_number": "R7778283004669"
    },
    "detail": "Payment Successful",
    "credits_consumed": 17100,
    "credits_available": 99990291739.42978,
    "id": 190508
}
</code></pre>

### Response Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| status | boolean | Transaction status |
| state | string | Transaction state |
| message | string | Transaction message |
| extra_data | object | Additional data (e.g., receipt number) |
| detail | string | Transaction detail |
| credits_consumed | float | Amount consumed in credits |
| credits_available | float | Remaining available credits |
| id | integer | Transaction ID |