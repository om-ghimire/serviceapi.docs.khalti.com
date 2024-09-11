# Sim TV API

## Overview

The Sim TV API provides functionalities for retrieving user details and processing payments for Sim TV services. It is designed to help you integrate Sim TV functionalities into your application or service. There are two primary endpoints available: one for looking up user details and another for processing payments.

- **User Detail API:** Retrieve the user's name and due amount.
- **Payment API:** Process payments for a specified amount.

## User Detail API

**URL:**  
`{{base_url}}/api/lookup/simtv/`

**Method:**  
GET

**Parameters:**  
<pre><code class="json">
{
  "token": "token provided",
  "customer_id": "customer_id of user, eg: 1000088047"
}
</code></pre>

**Success Response:**  
<pre><code class="json">
{
  "status": true,
  "data": {
    "customer_name": "YADAV PRD KHAREL",
    "due_amount": "0"
  }
}
</code></pre>

**Unsuccessful Response:**  
<pre><code class="json">
{
  "status": false,
  "error_code": "4000",
  "message": "Can't fulfill request",
  "error": "client_error",
  "details": "Invalid information",
  "error_data": {},
  "state": "Error"
}
</code></pre>

## Payment API

**URL:**  
`{{base_url}}/api/use/simtv/`

**Service Parameters:**  
<pre><code class="json">
{
  "customer_id": "Customer Id (e.g., 1000159157)",
  "token": "<token>",
  "reference": "<unique-reference>",
  "amount": "<amount>"
}
</code></pre>

**Valid Amounts:**  
<pre><code class="json">
[
  300, 325, 375, 400, 425, 475, 500, 550, 575, 600, 750, 800, 875, 975, 1000, 
  1050, 1065, 1125, 1190, 1275, 1425, 1440, 1625, 1875, 1900, 1950, 2000, 2125, 
  2250, 2375, 2550, 2875, 3250, 3800, 3900, 4250, 4275, 4500, 4750, 5000, 5100, 
  5175, 5750, 7000, 10000
]
</code></pre>

**Regex for Customer ID:**  
<pre><code class="json">
{
  "name": "Customer ID",
  "slug": "",
  "pattern": "([0-9]{10,11})",
  "error_message": "Invalid customer id"
}
</code></pre>

**Request:**  
<pre><code class="json">
{
  "token": "<token-provided>",
  "reference": "<unique-reference>",
  "amount": "<amount>",
  "customer_id": "<customer_id>"
}
</code></pre>

**Success Response:**  
<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {},
  "detail": "Transaction successful"
}
</code></pre>

**Unsuccessful Response:**  
<pre><code class="json">
{
  "error_code": "1010",
  "message": "Validation error",
  "status": false,
  "error_data": {},
  "details": ""
}
</code></pre>
