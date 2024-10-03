# Chitrawan Unique Net

This document outlines the API for **Chitrawan Unique Net** services, including details about the service, the methods to request information, and the payment process. It includes the request URLs, methods, parameters, and example success responses for both service details and payment.



## Service Details API

**Request URL:** `{{base_url}}/api/servicegroup/details/chitrawan-unique-net/`

**Request Method:** POST

### Request Params:

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "request_id": "khalti_test"
}
</code></pre>

### Success Response:

<pre><code class="json">
{
    "amount": 0,
    "customer_name": "Khalti Test",
    "phone": "9800000000",
    "address": "Basnetgaun, Lalitpur-04, Lalitpur",
    "packages": [
        {
            "amount": 1500,
            "package_id": 202,
            "name": "100 mbps 1 month"
        }
    ],
    "session_id": 26015,
    "status": true
}
</code></pre>

## Payment API

**Request URL:** `{{base_url}}/api/servicegroup/commit/chitrawan-unique-net/`

**Request Method:** POST

### Request Params:

<pre><code class="json">
{
  "reference": "{{$guid}}",
  "token": "{{token}}",
  "session_id": {{session_id}},
  "package_id": {{package_id}},
  "amount": {{package_amount}}
}
</code></pre>

### Success Response:

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "SUCCESS",
    "credits_consumed": 1500,
    "credits_available": 999999997280694,
    "id": 126362
}
</code></pre>
