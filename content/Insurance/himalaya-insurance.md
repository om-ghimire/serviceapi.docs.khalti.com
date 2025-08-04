
### Fetch Policy Details  
**POST**  
`{{base_url}}/api/servicegroup/details/primelife-insurance/`

#### Request Body

<pre><code class="json">
{
  "token": "{{token}}",
  "policy_no": "1000002888",
  "dob": "2049-05-14",
  "reference": "{{$guid}}"
}
</code></pre>

#### Response

<pre><code class="json">
{
  "premium_amount": 50723.0,
  "customer_name": "Krishal  Koirala",
  "address": "Ramdhuni-04,",
  "total_amount": 50723.0,
  "policy_no": "ULI2210001020",
  "product_name": "CHILD ENDOWMENT PLAN",
  "fine_amount": 0.0,
  "next_due_date": "2025-07-08",
  "current_due_date": "2025-07-08",
  "pay_mode": "Yearly",
  "session_id": 3464,
  "status": true
}
</code></pre>

---

## Make Payment  
**POST**  
`{{base_url}}/api/servicegroup/commit/primelife-insurance/`

#### Request Body

<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": "3464",
  "reference": "{{$guid}}",
  "amount": 50723
}
</code></pre>

#### Response

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {
    "assured_name": "Krishal  Koirala",
    "fine_amount": 0.0,
    "premium_amount": 50723.0,
    "next_due_date": "2026-07-08",
    "policy_no": "ULI2210001020",
    "total_amount": 50723.0,
    "invoice_number": "HLIRP900382830000347"
  },
  "detail": "Successful Payment",
  "credits_consumed": 50723.0,
  "credits_available": 99992949999.6798,
  "id": 166092
}
</code></pre>
