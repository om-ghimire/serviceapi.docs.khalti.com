## 8.7 Arrownet

### Multi-Step API

#### 1. User Details

**URL:** `{{base_url}}/api/servicegroup/details/arrownet/`

**Service Params:**

<pre><code class="json">
{
  "token": "token-provided",
  "username": "username"
}
</code></pre>

**Request Example:**

<pre><code class="json">
{
  "token": "your_token_here",
  "username": "Pradhanang"
}
</code></pre>

**Response:**

- **Success:**

<pre><code class="json">
{
  "status": true,
  "plan_details": [
    {
      "duration": 1,
      "amount": "1695.00"
    },
    {
      "duration": 3,
      "amount": "5085.00"
    },
    {
      "duration": 6,
      "amount": "9492.00"
    },
    {
      "duration": 12,
      "amount": "17628.00"
    }
  ],
  "days_remaining": 464,
  "current_plan": "50Mbps",
  "accept_advance_payment": true,
  "has_due": false,
  "full_name": "Ashish Pradhanang - Home"
}
</code></pre>

- **Error:**

  Note: For all client errors, `error_code` is `4000`.

<pre><code class="json">
{
  "status": false,
  "message": "Can't fulfill request",
  "state": "Error",
  "error": "client_error",
  "details": "Username not found",
  "error_data": {},
  "error_code": "4000"
}
</code></pre>

#### 2. Arrownet Payment

**URL:** `{{base_url}}/api/servicegroup/commit/arrownet/`

**Service Params:**

<pre><code class="json">
{
  "username": "username",
  "amount": "amount",
  "duration": "1,3,6,12",  // According to Requirement
  "reference": "unique value",
  "token": "token provided by khalti"
}
</code></pre>

**Request Example:**

<pre><code class="json">
{
  "username": "Pradhanang",
  "amount": "1695.00",
  "duration": 1,
  "reference": "unique_ref_123",
  "token": "your_token_here"
}
</code></pre>

**Response:**

- **Success:**

<pre><code class="json">
{
  "status": true,
  "message": "Successfully Completed Transaction",
  "detail": "Transaction successful",
  "extra_data": {},
  "state": "Success",
  "id": 1440
}
</code></pre>

- **Error:**

<pre><code class="json">
{
  "error_code": "1010",
  "message": "Validation error",
  "status": false,
  "error_data": {
    // present for validation error (codes 1010, 1011) specifying errors corresponding to fields
  },
  "details": "error details (string) for other errors"
}
</code></pre>
