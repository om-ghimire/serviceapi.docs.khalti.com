# Zoo Ticketing Service API Documentation

The **Zoo Service** allows you to fetch ticket types, make ticket purchases, and download purchased tickets. This documentation explains the API endpoints for ticket details, payments, and ticket downloads.

---

## Details Fetch

**URL:** `{{base_url}}/api/servicegroup/details/zoo/`

**Method:** POST

### Request Parameters

The following parameters are required in the POST request:

- **token:** Authentication token  
- **reference:** Unique reference ID for the request  

### Request Example

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "6447637f-6d27-45cb-be4f-93c9b34bb274"
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "details": [
        {"id": 1, "name": "Adult", "rate": 150},
        {"id": 2, "name": "Student", "rate": 90},
        {"id": 3, "name": "Children", "rate": 50},
        {"id": 4, "name": "Elderly Citizen", "rate": 90},
        {"id": 5, "name": "SAARC Adult", "rate": 250},
        {"id": 6, "name": "SAARC Children", "rate": 125},
        {"id": 7, "name": "Non-SAARC Adult", "rate": 750},
        {"id": 8, "name": "Non-SAARC Children", "rate": 375},
        {"id": 16, "name": "Check Dev", "rate": 1}
    ],
    "status": true
}
</code></pre>

### Response Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| details | array | List of ticket types with their IDs, names, and rates |
| details.id | integer | Unique ticket type ID |
| details.name | string | Ticket type name |
| details.rate | float | Ticket price per unit |
| status | boolean | Request status |

---

## Make Payment

**URL:** `{{base_url}}/api/servicegroup/commit/zoo/`

**Method:** POST

### Request Parameters

- **token:** Authentication token  
- **reference:** Unique reference ID for the transaction  
- **name:** Purchaser full name  
- **email:** Purchaser email  
- **mobile_number:** Purchaser mobile number  
- **products:** Array of purchased tickets (ticket ID and quantity)  

### Request Example

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "d77381c5-e770-4f88-90b2-c3bb52c358c4",
    "name": "Test test",
    "email": "test@gmail.com",
    "mobile_number": "9825666",
    "products": [
        {"product_id": 1, "quantity": 2},
        {"product_id": 3, "quantity": 4}
    ]
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Successfully created invoice",
    "credits_consumed": 500.0,
    "credits_available": 99988645313.4599,
    "id": 181427
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
| credits_consumed | float | Amount consumed for this transaction |
| credits_available | float | Remaining available credits |
| id | integer | Transaction ID / Invoice ID |

---

## Download Ticket

**URL:** `{{base_url}}/api/servicegroup/downloadticket/zoo/`

**Method:** POST

### Request Parameters

- **log_id:** Transaction / invoice ID  
- **token:** Authentication token  

### Request Example

<pre><code class="json">
{
    "log_id": 181461,
    "token": "OJqV4RQyx7ceCmqi69ae"
}
</code></pre>

### Response Example

<pre><code class="json">
{
    "status": true,
    "data": "JVBERi0xLjcKMSAwIG9iago8PCAvVHlwZSAvQ2F0YWxvZwovT3V0bGluZXMgMiAwIFIKL1BhZ2VzIDMgMCBSID4+CmVuZG9iagoyIDAgb2JqCjw8IC9UeXBlIC9PdXRsaW5lcyAvQ291bnQgMCA+PgplbmRvYmoKMyAwIG9iago8PCAvVHlwZSAvUGFnZXMKL0tpZHMgWzYgMCBSCjEyIDAgUgpdCi9Db3VudCAyCi9SZXNvdXJjZXMgPDwKL1Byb2NTZXQgNCAwIFIKL0ZvbnQgPDwgCi9GMSA4IDAgUgovRjIgOSAwIFIKPj4KL1hPYmplY3QgPDwgCi9JMSAxMCAwIFIKL0kyIDExIDAgUgovSTMgMTQgMCBSCi9JNCAxNSAwIFIKL0k1IDE2IDAgUgo+Pgo"
}
</code></pre>

### Response Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| status | boolean | Request status |
| data | string | Base64 encoded PDF / ticket file |
