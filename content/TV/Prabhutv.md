# Max TV API Documentation

## Overview

The Max TV API provides functionality for retrieving details about Max TV services and processing payments. The API consists of two main endpoints: one for fetching service details and another for making payments. These endpoints are designed to facilitate the integration of Max TV services into your application or system.

## Detail Fetch API

**Request URL:**  
`{{base_url}}/api/servicegroup/details/max-tv/`

**Request Method:**  
POST

**Service Parameters:**  
<pre><code class="json">
{
  "token": "<token>",
  "customer_id": "0000405146",  // Numeric value
  "reference": "<unique reference id>"
}
</code></pre>

**Response:**  
<pre><code class="json">
{
  "customer_name": "vod test All",
  "cid_stb_smartcard": "0000405146",
  "amount": 600,
  "tvs": [
    {
      "stb_no": "6030637000423863",
      "smartcard_no": "6030637000423863"
    }
  ],
  "session_id": 51,
  "status": true
}
</code></pre>

**Error Response:**  
<pre><code class="json">
{
  "status": false,
  "error_code": "4000",
  "message": "Can't fulfill request",
  "error": "client_error",
  "details": "Invalid customer id / stb no. / smartcard no.",
  "error_data": {},
  "state": "Error"
}
</code></pre>

## Payment API

**Request URL:**  
`{{base_url}}/api/use/max-tv/`

**Request Method:**  
POST

**Service Parameters:**  
<pre><code class="json">
{
  "token": "<token>",
  "customer_id": "0000405146",
  "amount": 100,
  "session_id": 51,
  "reference": "<unique reference id>"
}
</code></pre>

**Response:**  
<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {},
  "detail": "Successful",
  "id": 5035
}
</code></pre>
