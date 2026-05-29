# Nettv Cine Coupon

This service sells Nettv cine coupons. After a successful payment, the API returns the coupon code (PIN/serial). Integrators should send the PIN to the end customer via SMS and email.

--- 
**SMS content suggestion**

- Thank you for subscribing to Nettv cine via Khalti. Your coupon code is `{pin}`. Redeem it in the Nettv  app. T&C apply.

--- 

**Email content suggestion**

- **Subject:** Purchase Confirmation — Nettv cine Coupon Code

  Dear User,

  Thank you for subscribing to the Nettv cine coupon through Khalti.

  **Your Coupon Code:** `{pin}`

  To redeem your coupon, please apply the code within the Nettv app.

  Please note:

  - Coupons are valid only in the region where they are issued.
  - Coupon validity and applicable terms are governed by Nettv.

  If you need any assistance, please contact our support team.

  Best regards,  
  {Company name}

---

### 1. List Products
This API returns available Nettv cine coupon products.

**GET**  
`{{base_url}}/api/products/nettv-coupon/?token={{token}}`

#### Response

<pre><code class="json">
{
    "status": true,
    "data": [
        {
            "idx": "RFpPdchinv5moidep6PcA9",
            "name": "nettv coupon",
            "value": "nettv coupon",
            "amount": 2000
        }
    ]
}
</code></pre>

---

### 2. Payment
This endpoint processes the payment and returns the coupon PIN/serial.

**POST**  
`{{base_url}}/api/use/nettv-coupon/`

#### Request Body

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "value": "nettv coupon",
    "amount": 200
    "phone_number": 9860848045, //optional
    "email": "a@gmail.com" //optional
}
</code></pre>

#### Success Response

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Your Pin number is 'c3'",
  "serial": "c3",
  "pin": "c3",
  "credits_consumed": xxx.xx,
  "credits_available": xxxx.xx,
  "id": 176925
}
</code></pre>


#### Failed Response

### Invalid Product Value

<pre><code class="json">
{
    "status": false,
    "error_code": "1010",
    "message": "Validation error",
    "error": "invalid_parameters",
    "details": {
        "value": "Invalid value for product"
    },
    "error_data": {
        "value": "Invalid value for product"
    },
    "state": "Error"
}
</code></pre>


### Invalid Amount

<pre><code class="json">
{
    "status": false,
    "error_code": "1010",
    "message": "Validation error",
    "error": "invalid_parameters",
    "details": {
        "amount": "enter valid amount "
    },
    "error_data": {
        "amount": "enter valid amount "
    },
    "state": "Error"
}
</code></pre>





### Product Out of Stock / Unavailable

<pre><code class="json">
{
    "status": false,
    "error_code": "4000",
    "message": "Can't fulfill request",
    "error": "client_error",
    "details": "Product Currently Unavailable",
    "error_data": {},
    "state": "Error"
}
</code></pre>

### Duplicate Reference ID

<pre><code class="json">
{
    "status": false,
    "error_code": "1013",
    "message": "Request with duplicate reference id obtained",
    "error": "duplicate_request",
    "details": "",
    "error_data": {},
    "state": "Error"
}
</code></pre>
