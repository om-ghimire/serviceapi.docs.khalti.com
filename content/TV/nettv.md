# Nettv API

## Overview
The Nettv API allows you to interact with the Nettv service, providing functionality for fetching details, getting package rates, and processing payments. This documentation outlines the available endpoints, methods, and expected responses.

---

## Details Fetch

**URL**: `{{base_url}}/api/servicegroup/details/nettv-v3/`  
**Method**: POST  

**Service Body Params**:
<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}",
  "username": "krustykrab"
}
</code></pre>

### Success Response
<pre><code class="json">
{
  "status": true,
  "stb_list": [
    {
      "serial": "00226D85984E"
    },
    {
      "serial": "00226DAB66F1"
    },
    {
      "serial": "D4226DBB50F4"
    }
  ],
  "username": "krustykrab",
  "session_id": 27817
}
</code></pre>

---

## Get Packages

**URL**: `{{base_url}}/api/servicegroup/getpackagerates/nettv-v3/`  
**Method**: POST  

**Service Params**:
<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": "25527",
  "serial_no": "00226D85984E"
}
</code></pre>
## Success Response 
<pre><code class="json">
{
  "status": true,
  "username": "west",
  "stb": "00226D86F6DD",
  "package_status": "inactive",
  "expiry_date": "",
  "package_name": "",
  "stb_type": "primary",
  "user_id": 424981,
  "package_list": [
    {
      "name": "Platinum - Introductory 1 month",
      "duration": "1",
      "package_price": 221.0,
      "discount": 0.0,
      "amount": 250.0,
      "package_sales_id": 123,
      "package_id": 1
    },
    {
      "name": "Platinum - Introductory 3 month",
      "duration": "3",
      "package_price": 663.0,
      "discount": 0.0,
      "amount": 750.0,
      "package_sales_id": 0,
      "package_id": 1
    },
    {
      "name": "Platinum - Introductory 12 month",
      "duration": "12",
      "package_price": 2654.0,
      "discount": 0.0,
      "amount": 3000.0,
      "package_sales_id": 0,
      "package_id": 1
    }
  ],
  "session_id": 25527
}
</code></pre>


## Payment

**URL**: `{{base_url}}/api/servicegroup/commit/nettv-v3/`  
**Method**: POST  

**Service Params**:
<pre><code class="json">
{
  "token": "{{token}}",
  "package_sales_id": "{{package_sales_id}}",
  "session_id": "{{session_id}}",
  "reference": "{{$guid}}"
}
</code></pre>

### Success Response
<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {},
  "detail": "Transaction Successful",
  "credits_consumed": 250.0,
  "credits_available": -220.93,
  "id": 130121
}
</code></pre>
