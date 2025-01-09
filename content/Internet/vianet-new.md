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
  "status": true,
  "details": {
    "message": "Success",
    "amount": 27719,
    "policy_no": "63190031433",
    "customer_name": "Aayushma Malla",
    "product_name": "Child Endowment(Bal Umanga)",
    "interest_rate": "12.00",
    "loan_amount": "32000.00",
    "loan_date": "2023-02-02",
    "principal_amount": "27628.00",
    "request_id": "63190031433-2016",
    "interest": "91.00"
  },
  "session_id": 12341
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
