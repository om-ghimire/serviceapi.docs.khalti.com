# Nepal Life Insurance

### **User Detail Fetch API**

**Request URL:** `{{base_url}}/api/servicegroup/details/nepal-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{TOKEN}}",
    "reference": "unique reference id",
    "policy_no": "401059698",
    "dob": "2008-03-20"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "customer_name": "TUSARA SINGH THAKURI",
    "policy_no": "401059698",
    "due_date": "2020-12-20",
    "premium_amount": 2500.0,
    "amount": 2500.0,
    "fine_amount": 0.0,
    "rebate_amount": 0.0,
    "session_id": 102,
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
    "details": "Policy does not exist or not active.",
    "error_data": {},
    "state": "Error"
}
</code></pre>

---

### **Payment API**

**Request URL:** `{{base_url}}/api/servicegroup/commit/nepal-life-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{TOKEN}}",
    "reference": "unique reference id",
    "amount": 2500,
    "session_id": 2121345
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "policy_no": "401059698"
    },
    "detail": "Success",
    "credits_consumed": 2500.0,
    "credits_available": 105844058.084999,
    "id": 10959
}
</code></pre>
