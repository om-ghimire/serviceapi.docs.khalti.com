# Code Himalayan EMI Service API Documentation

The **Code Himalayan EMI Service** allows you to fetch customer loan details and make EMI payments for products financed through **Hulas Fin Serve Ltd**. This documentation explains the API endpoints used to retrieve loan details and process payments.

---

## Details Fetch

**URL:** `{{base_url}}/api/servicegroup/details/code-himalayan-emi/`

**Method:** POST

### Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token  
- **reference:** Unique reference ID for the request  
- **request_id:** Customer request or loan identifier  
- **service_slug:** Service identifier (example: `hulas-fin-serve-ltd`)  

### Request Example

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "7f3daf55-6cd5-4d61-a4ae-1b565cc414ee",
    "request_id": "001SIF52004387",
    "service_slug": "hulas-fin-serve-ltd"
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "customer_name": "Milan-2",
    "address": "Pranil",
    "product_name": null,
    "model": "PULSAR 150",
    "due_from": "2024-08-27",
    "next_installment_date": "2024-08-27",
    "next_installment_amount": 0,
    "disbursedAmount": 150000,
    "installmentAmount": 0,
    "outstandingPrincipal": 0,
    "principalDue": -20,
    "interestDue": 20,
    "penaltyDue": 0,
    "chargesDue": 0,
    "dealerName": null,
    "savingBalance": 0,
    "totalDue": 0,
    "session_id": 25837,
    "status": true
}
</code></pre>

### Response Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| customer_name | string | Customer full name |
| address | string | Customer address |
| product_name | string | Name of financed product |
| model | string | Product model |
| due_from | string | Start date of due period |
| next_installment_date | string | Date of next EMI installment |
| next_installment_amount | float | Amount of next installment |
| disbursedAmount | float | Loan disbursed amount |
| installmentAmount | float | Regular installment amount |
| outstandingPrincipal | float | Remaining principal balance |
| principalDue | float | Principal due amount |
| interestDue | float | Interest due amount |
| penaltyDue | float | Penalty due amount |
| chargesDue | float | Additional charges due |
| dealerName | string | Dealer name (if applicable) |
| savingBalance | float | Customer saving balance |
| totalDue | float | Total amount due |
| session_id | integer | Session identifier for payment |
| status | boolean | Request status |

---

## Make Payment

**URL:** `{{base_url}}/api/servicegroup/commit/code-himalayan-emi/`

**Method:** POST

### Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token  
- **reference:** Unique reference ID for the transaction  
- **session_id:** Session ID obtained from the details endpoint  
- **amount:** Payment amount  

### Request Example

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "33ff99c3-ecec-44da-b589-94bd8057400a",
    "session_id": 25837,
    "amount": 100
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "status": false,
    "error_code": "4000",
    "message": "Can't fulfill request",
    "error": "client_error",
    "details": "Loan payment received successfully",
    "error_data": {},
    "state": "Error"
}
</code></pre>

### Response Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| status | boolean | Transaction status |
| error_code | string | Error code if transaction failed |
| message | string | Error or success message |
| error | string | Type of error (`client_error`, `server_error`, etc.) |
| details | string | Additional details about transaction |
| error_data | object | Extra error-related data |
| state | string | Transaction state (`Success` or `Error`) |