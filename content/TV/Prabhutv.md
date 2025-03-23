# Prabhu TV API Documentation  

## Overview  

This document describes the API endpoints for fetching customer details and processing payments for Prabhu TV services. It includes request and response formats for both the **Customer Detail Fetch API** and the **Payment API**.  

---

## Customer Detail Fetch API  

**Request URL:** `{{base_url}}/api/servicegroup/details/prabhu-tv/`  
**Request Method:** `POST`  

### Valid Amounts  

`[350, 1050, 1800, 2400, 3500, 6500, 9000, 11500, 24000]`  

### Service Params  

<pre><code class="json">
{
    "token": "token",
    "reference": "reference123",
    "cas_id": "01234567891"
}
</code></pre>  

### Response  

<pre><code class="json">
{
    "session_id": 10,
    "customer_name": "Online Test Box Five",
    "balance": "141.94",
    "stb_count": "1",
    "customer_id": "102995",
    "current_packages": [
        {
            "product_name": "Lumbini(12 Months)",
            "service_start_date": "2020-05-06",
            "serial_number": "00720922966",
            "mac_vc_number": "02532963573",
            "expiry_date": "2020-05-23",
            "bill_amount": 168
        }
    ],
    "status": true
}
</code></pre>  

### Error Response  

<pre><code class="json">
{
    "status": false,
    "error_code": "4001",
    "message": "Invalid Customer ID",
    "error": "client_error",
    "details": "The provided cas_id does not exist.",
    "error_data": {},
    "state": "Error"
}
</code></pre>  

---

## Payment API  

**Request URL:** `{{base_url}}/api/use/prabhu-tv/`  
**Request Method:** `POST`  

### Valid Amounts  

`[350, 1800, 2400, 3500, 6500, 9000, 11500, 24000]`  

### Service Params  

<pre><code class="json">
{
    "token": "token",
    "cas_id": "01234567891",
    "session_id": 10,
    "amount": 10,
    "reference": "reference123"
}
</code></pre>  

### Response  

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Transaction Successful",
    "credits_consumed": 10.0,
    "credits_available": 97917526.975,
    "id": 2771
}
</code></pre>  

### Error Response  

<pre><code class="json">
{
    "status": false,
    "error_code": "4002",
    "message": "Invalid Amount",
    "error": "client_error",
    "details": "The provided amount is not valid for this transaction.",
    "error_data": {},
    "state": "Error"
}
</code></pre>  
