# **Arhant Non-Life Insurances**

**Overview:** This document provides information on the non-life insurance services offered by Arhant, including the endpoints for retrieving proforma details and completing payments.

**Available Non-Life Insurance Services:**

1. ##### **Shikhar Insurance**
   - **Service Slug:** `shikhar-insurance`

2. ##### **United Insurance**
   - **Service Slug:** `united-ajod-insurance`

**API for Retrieving Proforma Details** ``{{base_url}}/api/servicegroup/details/arhant-non-life-insurance/``

**Method:** POST

**Request Parameters:**
To get the proforma details, send a POST request with the following parameters:
<pre><code class="json">
{
    "token": "token",              
    "reference": "reference",      
    "proforma_no": "01458110",       
    "service_slug": "service_slug" 
}
</pre>

**Example Response:**
The response provides detailed information about the proforma, such as premium amounts, insured details, and vehicle information.
<pre><code class="json">
{
    "success_message": "Proforma is valid",
    "request_id": 2176242,
    "proforma_no": "2176242",
    "class_name": "Motor,Third Party Motorcycle",
    "sum_insured": 0,
    "net_premium": 1700,
    "stamp_duty": 10,
    "vat_amount": 221,
    "subsidized_premium": 0,
    "total_premium": 1931,
    "vehicle_no": "NA 59 PA 2511",
    "insured": "Tanknath Pokharel,Hariwan-01, Sarlahi",
    "session_id": 20327,
    "status": true
}
</pre>

**API for Completing Payment**

**Endpoint:** Complete Payment: {{base_url}}/api/servicegroup/commit/arhant-non-life-insurance/

**Method:** POST

**Request Parameters:**
To finalize the payment, send a POST request with these parameters:
<pre><code class="json">
{
    "token": "token",               
    "reference": "reference",        
    "session_id": "session_id"     
}
</pre>

**Example Response:**
The response confirms the transaction status and provides details about credits consumed and remaining.
<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Success",
    "credits_consumed": 4803,
    "credits_available": "xxxxxxxx",
    "id": 62849
}
</pre>
