# **Himchuli Electricity**

**Type: Multi-Step API**

**Service_slug: himchuli**

### 1. **Detail Fetch API**

**Request URL:** {{base_url}}/api/servicegroup/details/easternhawk/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "token",
  "reference": "Unique Identifier",
  "service_slug": "himchuli",
  "customer_number": "356"
}
</code></pre>

**Response:**

<pre><code class="json">
{
  "amount": "1708.00",
  "customer_id": "567",
  "name": "Gyan bahadur majhi",
  "capacity": "15A",
  "area": "03-7430",
  "session_id": 2318,
  "status": true
}
</code></pre>

**Fields:**

- **amount**: The total amount due for payment.
- **customer_id**: The unique identifier for the customer.
- **name**: The name of the customer.
- **capacity**: The electrical capacity (e.g., "15A").
- **area**: The area code or identifier for the location.
- **session_id**: The unique session ID for the transaction.
 

### 2. **Payment API**

**Request URL:** {{base_url}}/api/servicegroup/commit/easternhawk/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "token",
  "amount": "1708.00",
  "reference": "Unique Reference",
  "session_id": "2318"  <!-- session id obtained from detail fetch API -->
}
</code></pre>

**Response:**

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {},
  "detail": "Success",
  "credits_consumed": 400.0,
  "credits_available": 9999558289.38,
  "id": 36219
}
</code></pre>

**Fields:**

 
- **state**: The state of the transaction (`Success`).
- **message**: A message indicating the result of the transaction (`Successfully Completed Transaction`).
- **extra_data**: Any additional data related to the transaction.
- **detail**: Additional details about the payment, including a confirmation message (`Success`).
- **credits_consumed**: The total credits consumed for this transaction.
- **credits_available**: The total credits available after this transaction.
- **id**: The unique ID associated with the transaction.


