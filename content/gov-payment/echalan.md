# **GovPayment (eChalan / Government Voucher Payment)**

**Type:** Single-Step / Direct Payment API

This API is used for validating and preparing payment for government vouchers / eChalans (traffic fines).


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
  "amount": "500",
  "service": "echalan",
  "province_code": "123",
  "district_code": "123",
  "fiscal_year": "123"
}
</code></pre>

Field descriptions:

| Field           | Type   | Required    | Description                                                                 | Example             |
|-----------------|--------|-------------|-----------------------------------------------------------------------------|---------------------|
| token           | string | Yes         | Authentication token                                                        | —                   |
| reference       | string | Yes         | Unique transaction reference (usually GUID)                                 | 123e4567-e89b-...   |
| app_id          | string | Yes         | Merchant/application identifier                                             | MER-7-APP-11        |
| voucher_no      | string | Yes         | Voucher / Chit / eChalan number                                             | 2078-232544         |
| amount          | string | Yes         | Claimed / entered amount (sent as string)                                   | "500"               |
| service         | string | Yes         | Service identifier                                                          | echalan             |
| province_code   | string | Yes         | Province code (required for some services)                                  | "1" or "123"        |
| district_code   | string | Yes         | District code (required for some services)                                  | "123"               |
| fiscal_year     | string | Yes         | Fiscal year code (required for revenue/voucher services)                    | "078/79" or "123"   |

**Response:**

<pre><code class="json">
{
    "validity": true,
    "creditor_name": "",
    "app_id": "GON-7-TVRS-1",
    "description": "",
    "full_name": "SURAJ BK",
    "amount": 2000,
    "vehicle_category": "1234",
    "tracing_id": "AA8-M",
    "voucher_no": "1234",
    "bank_code": "1234",
    "chit_number": "808100201641071",
    "ebp_number": "1234",
    "session_id": 3792,
    "status": true
}
</code></pre>

### Key Response Fields

| Field            | Meaning / Usage                                                                                   |
|------------------|---------------------------------------------------------------------------------------------------|
| validity         | `true` = voucher exists and is valid for payment|
| amount           | **Official / due amount** — **this value must be used** for the actual payment (not the input amount) |
| full_name        | Name of the person / vehicle owner / taxpayer associated with the voucher                        |
| session_id       | Required for the commit / payment step                                                            |
| chit_number      | Often the actual fine / challan / voucher reference                                               |
| tracing_id       | Internal tracking ID (can be shown to user for reference)                                         |
| status           | Overall API success flag (`true` = valid response received)                                       |



## 2. Payment / Commit API (assumed pattern – adjust if different)

**Request URL:** `{{base_url}}/api/servicegroup/commit/govpayment/`

**Request Method:** POST

**Service Params (example):**

<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": "3792",
  "amount": 2000
}
</code></pre>



**Success Response (example):**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Successful Transaction",
    "credits_consumed": 500.0,
    "credits_available": 99988714602.9099,
    "id": 180502
}
</code></pre>