# BPC API

## Overview

The BPC API allows you to retrieve counter information, get detailed bill data for a consumer, and make payments for due bills. All endpoints require POST requests with authentication tokens.

---

## Get Counters

**URL:** `{{base_url}}/api/servicegroup/counters/bpc/`  
**Method:** POST

### Request Parameters

- **token:** Authentication token

### Request Example

<pre><code class="json">
{
  "token": "{{token}}"
}
</code></pre>

### Success Response Format

<pre><code class="json">
{
  "status": true,
  "counters": [
    {
      "name": "BPC Waling",
      "value": "1:bpc-waling"
    },
    {
      "name": "BPC Galyang",
      "value": "3:bpc-galyang"
    }
  ]
}
</code></pre>

---

## Get Bill Details

**URL:** `{{base_url}}/api/servicegroup/details/bpc/`  
**Method:** POST

### Request Parameters

- **token:** Authentication token  
- **reference:** Unique transaction reference  
- **consumer_no:** Consumer number  
- **counter_code:** Counter code from the counters API (e.g., "1:bpc-waling")  
- **consumer_id:** Internal consumer ID

### Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}",
  "consumer_no": "0005.0007.000268",
  "counter_code": "1:bpc-waling",
  "consumer_id": 1246
}
</code></pre>

### Success Response Format

<pre><code class="json">
{
  "consumer_name": "Til Bahadur Rana",
  "consumer_id": 1549,
  "address": "Syangja-Jagatradevi,8",
  "meter_name": "Domestic 5 Amp[1001]",
  "total_due_amount": 1251.8,
  "due_bills": [
    {
      "bill_no": "131434",
      "bill_date": "2077/08/21",
      "bill_amount": 471,
      "description": "Bill of 2077/8",
      "sur_charge_amount": 47.1,
      "total_amount": 518.1
    },
    {
      "bill_no": "140985",
      "bill_date": "2077/09/22",
      "bill_amount": 350,
      "description": "Bill of 2077/9",
      "sur_charge_amount": 35,
      "total_amount": 385
    },
    {
      "bill_no": "150219",
      "bill_date": "2077/10/25",
      "bill_amount": 317,
      "description": "Bill of 2077/10",
      "sur_charge_amount": 31.7,
      "total_amount": 348.7
    }
  ],
  "session_id": 690,
  "status": true
}
</code></pre>

---

## Payment

**URL:** `{{base_url}}/api/servicegroup/commit/bpc/`  
**Method:** POST

### Request Parameters

- **token:** Authentication token  
- **session_id:** Session ID from bill details API  
- **amount:** Amount to pay  
- **reference:** Unique transaction reference

### Request Example

<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": 690,
  "amount": 1251.8,
  "reference": "{{$guid}}"
}
</code></pre>

### Success Response Format

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {
    "receipt_no": 425419,
    "receipt_date": "2082/04/19"
  },
  "detail": "Due bill amount paid successfully. Please download the receipt from Transaction History.",
  "credits_consumed": 1251.8,
  "credits_available": 9999.99,
  "id": 166079
}
</code></pre>
