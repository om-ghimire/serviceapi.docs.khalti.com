# Electricity Payment API Documentation

## Overview
This document provides details on how to interact with the Electricity Payment APIs. The process involves retrieving counters, fetching bill details, calculating service charges, and making payments.

## 1. Get Counters

**URL:** `{{base_url}}/api/servicegroup/counters/nea/`  
**Method:** POST  

**Request Body:**
<pre><code class="json">
{
    "token": "token"
}
</code></pre>

### Success Response
<pre><code class="json">
{
    "status": true,
    "counters": [
        {
            "name": "AANBU DC",
            "value": "243:aanbu-dc"
        },
        {
            "name": "ACHHAM DC",
            "value": "391:achham-dc"
        },
        {
            "name": "RATNAPARK DC",
            "value": "201:ratnapark-dc"
        }
    ]
}
</code></pre>

**2. Get details API**

**URL**:``{{url}}/api/servicegroup/details/nea/`` 

**Request**: ``POST``

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "Sc_no": "customer SC number, e.g. 02A.12.512",
    "reference": "unique-reference",
    "Office_code":"one of the 'value' fields from Get Counters response",
    "consumer_id": "consumer ID, e.g. 3042"
}
</code></pre>

**Note : Sc\_no : 3 alphanumeric string separated by dot.**

## Success Response
<pre><code class="json">
{
    "session_id": 5,
    "consumer_name": "Michael Jackson",
    "due_bills": [
        {
            "bill_amount": "200",
            "bill_date": "2017-02-24",
            "days": 5,
            "payable_amount": 200,
            "due_bill_of": "2073 Magh",
            "status": "Normal"
        },
        {
            "bill_amount": "200",
            "bill_date": "2017-02-24",
            "days": 13,
            "payable_amount": 250,
            "due_bill_of": "2073 Falgun",
            "status": "-25% Penalty"
        }
    ],
    "total_due_amount": 450,
    "status": true
}
</code></pre>

!!! Important
    + The minimum payable amount for NEA (Electricity) is the due amount of the oldest bill. 
    + For the provided bill details, the minimum payable amount is `200` (2073 Magh). 
    + Partial payments are allowed.


**3**.**Get service charge**  

**URL**:`` {{url}}/api/servicegroup/servicecharge/nea/``

**Request**: ``POST``

**Service Params:**  
<pre><code class="json">
{
    "amount": "Total amount intended to pay",
    "session_id": "value obtained during detail fetch step",
    "token": "Unique Identifier"
}
</code></pre>

## Success Response
<pre><code class="json">
{
    "service_charge": 5.0,
    "amount": 600.0,
    "status": true
}

</code></pre>
**Description:**  
Calculate the service charge for the payment amount. The service charge applies only for amounts greater than 500.

**Note:**  
- For amounts less than 500, the service charge is 0.
- This API only calculates the charge. The amount provided to the Make Payment API should exclude the service charge.

**4**. **Make Payment**

**URL**: ``{{url}}/api/servicegroup/commit/nea/``

**Method:** ``POST``

**Response Body**
<pre><code class="json">
{
    "amount": "Total amount intended to pay (excluding service charge)",
    "session_id": "value obtained during detail fetch step",
    "reference": "unique reference"
}
</code></pre>


### Success Response
<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Amount Paid Successfully",
    "credits_consumed": 600.0,
    "credits_available": 9996,
    "id": 61892
}
</code></pre>

### Error Response 
<pre><code class="json">
{
    "status": false,
    "error_code": "4000",
    "message": "Can't fulfill request",
    "error": "client_error",
    "details": "Max number exceeding",
    "error_data": {},
    "state": "Error"
}
</code></pre>