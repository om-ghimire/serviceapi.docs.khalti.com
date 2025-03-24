# Vianet 

## 1. Service Group Details API

### URL
`{{base_url}}/api/servicegroup/details/vianet-updated/`

### Method
`POST`

### Request Payload
<pre><code class="json">
{
  "token": "token",
  "reference": "Unique reference",
  "customer_id": 110871
}
</code></pre>

### Success Response
<pre><code class="json">
{
    "customer_id": 110871,
    "customer_name": "Suman  Shrestha",
    "bills": [
        {
            "payment_id": "1613142_PP",
            "service_name": "wetherspooncafe21424",
            "service_details": "FiberNet Home CRush (1 year)",
            "vat_amount": "30.55",
            "grand_total": "277.98",
            "service_rate": "246.00"
        },
        {
            "payment_id": "1613143_PP",
            "service_name": "wetherspooncafe21424",
            "service_details": "Test payment 2",
            "vat_amount": "3.77",
            "grand_total": "34.35",
            "service_rate": "30.40"
        },
        {
            "payment_id": "1613144_PP",
            "service_name": "wetherspooncafe21424",
            "service_details": "Test Payment 1",
            "vat_amount": "5.20",
            "grand_total": "47.46",
            "service_rate": "42.00"
        },
        {
            "payment_id": "1613145_PP",
            "service_name": "wetherspooncafe21424",
            "service_details": "FiberNet Home CRush (6 months)",
            "vat_amount": "13.00",
            "grand_total": "118.65",
            "service_rate": "105.00"
        }
    ],
    "session_id": 27383,
    "status": true
}
</code></pre>

### Error Response
<pre><code class="json">
{
  "status": false,
  "error_code": "7000",
  "message": "Unknown Error occured. Check details",
  "error": "unknown_error",
  "details": "You have no pending bills right now !!",
  "error_data": {},
  "state": "Error"
}
</code></pre>

---

## 2. Payment Commit API

### URL
`{{base_url}}/api/servicegroup/commit/vianet-updated/`

### Method
`POST`

### Request Payload
<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": "{{session_id}}",
  "payment_id": "{{payment_id}}",
  "amount": {{amount}},
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
  "detail": {
    "message": "Payment Successfull! Thank you for using Online Payment Option"
  },
  "credits_consumed": 277.98,
  "credits_available": 999006795.14,
  "id": 130144
}
</code></pre>

### Error Response
<pre><code class="json">
{
  "status": false,
  "error_code": "4000",
  "message": "Can't fulfill request",
  "error": "client_error",
  "details": "Payment seems to have already been Made!",
  "error_data": {},
  "state": "Error"
}
</code></pre>
