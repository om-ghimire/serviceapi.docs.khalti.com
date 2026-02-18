# **GovPayment (Government Voucher / Revenue Payment)**


**Type:** Two-Step API (Validation → Commit)

This API handles validation and payment of government revenue vouchers, internal revenue deposits, fines, fees, and similar transactions processed through various Nepalese government portals (e.g., FCGO, IRD, provincial/municipal payments).

## Available Services

These government services are supported via the GovPayment API:

| Service Name                              |
|-------------------------------------------|
| No Objection Letter / Certificate         |
| Inland Revenue Department                 |
| Government Revenue                        |
| Department of Passport                    |
| Department of Consular                    |
| Office of Company Registration            |
| Loksewa (Kendra / Pradesh)                |

## 1. Detail Fetch & Validation API

**Request URL:** `{{base_url}}/api/servicegroup/details/govpayment/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}",
  "app_id": "MER-7-APP-11",
  "voucher_no": "2078-232544",
  "amount": "500"
}
</code></pre>

Field descriptions:

| Field       | Type   | Required | Description                                                                 | Example              |
|-------------|--------|----------|-----------------------------------------------------------------------------|----------------------|
| token       | string | Yes      | Authentication token                                                        | —                    |
| reference   | string | Yes      | Unique transaction reference (GUID recommended)                             | 123e4567-e89b-...    |
| app_id      | string | Yes      | Merchant / application identifier provided by the gateway                   | MER-7-APP-11         |
| voucher_no  | string | Yes      | Voucher number, challan number, or revenue reference number                 | 2082-7954134/326023501 |
| amount      | string | Yes      | Amount entered by the user (sent as string)                                 | "500"                |

**Response:**

<pre><code class="json">
{
    "validity": true,
    "creditor_name": "KA.1.1 RAJASWO, ANUDAN TATHA BIBIDH PRAPTI KHATA (FCGO)",
    "debitor_name": "SPARROW PAY PVT LTD",
    "app_id": "GON-6-GIBL-FDRL",
    "voucher_no": "2082-7954134/326023501",
    "remarks": "326023501",
    "particulars": "Nar Kumar Limbu",
    "amount": 500.0,
    "organization": null,
    "session_id": 3793,
    "status": true
}
</code></pre>

### Key Response Fields

| Field         | Meaning / Usage                                                                                   |
|---------------|---------------------------------------------------------------------------------------------------|
| validity      | `true` = voucher is valid and payable                                                             |
| amount        | **Official / confirmed amount** — this value **must** be used for payment (may differ from input) |
| particulars   | Name / description of the payer / purpose (often shown to user)                                   |
| creditor_name | Receiving government office / account name                                                        |
| session_id    | Required for the commit / payment step                                                            |
| status        | Overall API success flag                                                                          |



## 2. Payment / Commit API

**Request URL:** `{{base_url}}/api/servicegroup/commit/govpayment/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": "3793",
  "amount": 500,
  "reference": "{{$guid}}"
}
</code></pre>

**Important Notes on Amount:**
- Use the `amount` value **returned in the details response** and the amount the user originally entered. For test Use amount **500** only 
- Sending a different amount than the validated one will likely result in failure.

**Success Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Successful Transaction",
    "credits_consumed": 500.0,
    "credits_available": 99988713602.9099,
    "id": 180504
}
</code></pre>





