# Bluebook API

## Overview

The Bluebook API allows users to calculate and process bluebook renewals for vehicles. It consists of two main steps: the Calculate API and the Payment API. The Calculate API computes the required renewal charges, while the Payment API handles the transaction based on the results from the Calculate API.

## **Type: Multi Step API**

### 1. **Calculate API**

**Request URL:** `{{base_url}}/api/servicegroup/calculate/bluebook-renewal/`

**Request Method:** POST

**Service Params:** 

<pre><code class="json">
{
    "token": "token",
    "reference": "unique reference",
    "vehicle_type": "vehicle_type",  // 4W, 2W
    "cc": "cc",
    "valid_start_date": "valid_start_date",
    "valid_end_date": "valid_end_date",
    "manufacture_date": "manufacture_date",
    "thirdparty_insurance": "True/False"
}
</code></pre>

**Response:**  

<pre><code class="json">
{
    "status": true,
    "detail": {
        "unpaid_tax": 10000,
        "unpaid_tax_fine_amt": 4720.0,
        "tax_cy": 0,
        "tax_fine_cy": 0.0,
        "renewal_charge": 600,
        "renewal_fine": 600,
        "modal_tax": 4750,
        "total": 20670,
        "service_charge": 0,
        "insurance": 1935,
        "total_amount": 22605
    },
    "session_id": 25871
}
</code></pre>

---

### 2. **Payment API**

**Request URL:** `{{base_url}}/api/servicegroup/commit/bluebook-renewal/`

**Request Method:** POST

**Note:** 
- If `thirdparty_insurance` is true in the Calculate API, you need to pass `document_back_image` and `document_front_image` in the Payment API params.
- If `thirdparty_insurance` is false, you need to pass `insurance_paper` in the Payment API params.

**Service Params:** 

<pre><code class="json">
{
    "token": "token",
    "session_id": "session_id",
    "full_name": "full name",
    "contact_no": "contact_no>",
    "email": "test@test.com",
    "pick_location": "pick_location",
    "city": "City",
    "vehicle_no": "vehicle_no",
    "document_back_image": "document_back_image", // base 64 image
    "document_front_image": "document_front_image", // base 64 image
    "insurance_paper": "insurance_paper" // base 64 image
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "detail": "Transaction Completed.",
    "message": "Transaction Completed",
    "credits_consumed": 22605.0,
    "credits_available": 999999998507583.0,
    "extra_data": {
        "session_id": "25871",
        "full_name": "Test test",
        "contact_no": "9863636999",
        "email": "test@khalti.com",
        "pick_location": "location",
        "city": "City",
        "vehicle_no": "11221",
        "document_front_image": "https://cdn.example.com/media/bluebook/document_front_image_12345.png",
        "document_back_image": "https://cdn.example.com/media/bluebook/document_back_image_12345.png"
    },
    "id": 126284
}
</code></pre>
