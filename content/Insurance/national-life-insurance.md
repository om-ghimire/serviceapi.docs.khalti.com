##  Endpoint: National Life Insurance

###  Fetch Policy Details  
**POST**  
`{{base_url}}/api/servicegroup/details/national-life-insurance/`

#### Request Body

<pre><code class="json">
{
  "token": "{{token}}",
  "policy_no": "043003318",
  "dob": "1985-05-15",
  "reference": "{{$guid}}"
}
</code></pre>

#### Response

<pre><code class="json">
{
  "premium_amount": 100.0,
  "customer_name": "test  test1",
  "address": "Malakheti",
  "total_amount": 180.0,
  "policy_no": "701000000052",
  "product_name": "Endowment Cum Whole Life Plan - Amulya",
  "fine_amount": 80.0,
  "next_due_date": "2020-04-24",
  "current_due_date": "2020-04-24",
  "pay_mode": "Yearly",
  "session_id": 3465,
  "status": true
}
</code></pre>

---

###  Make Payment  
**POST**  
`{{base_url}}/api/servicegroup/commit/national-life-insurance/`

#### Request Body

<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": 3465,
  "amount": 180,
  "reference": "{{$guid}}"
}
</code></pre>

#### Response

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {
    "assured_name": "test  test1",
    "fine_amount": 80.0,
    "premium_amount": 100.0,
    "next_due_date": "2026-07-15",
    "policy_no": "701000000052",
    "total_amount": 180.0,
    "invoice_number": "RP557828300246"
  },
  "detail": "Successful Payment",
  "credits_consumed": 180.0,
  "credits_available": xxxxxxxxx.6798,
  "id": 166094
}
</code></pre>
