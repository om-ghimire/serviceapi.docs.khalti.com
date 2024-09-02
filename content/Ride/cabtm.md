# **12.2 CABTM**

**Type: Multi-Step API**

### 1. **Detail Fetch API**

**Request URL:** http://uatservices.khalti.com/api/servicegroup/details/cabtm/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "token",
  "reference": "Unique Identifier",
  "mobile_number": "9779821587036"
}
</code></pre>

**Response:**

<pre><code class="json">
{
  "customer_name": "Test Shrestha",
  "balance": 578.56,
  "mobile_number": "+9779821587036",
  "status": true,
  "dob": "1994-09-30",
  "role": "driver",
  "session_id": 2319
}
</code></pre>

**Fields:**

- **customer_name**: The name of the customer.
- **balance**: The current balance of the customer.
- **mobile_number**: The mobile number of the customer.
- **status**: Indicates whether the API call was successful (`true`).
- **dob**: The date of birth of the customer.
- **role**: The role of the customer (e.g., "driver").
- **session_id**: The unique session ID for the transaction.

### 2. **Payment API**

**Request URL:** http://uatservices.khalti.com/api/servicegroup/commit/cabtm/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "<token>",
  "mobile_number": "9779821587036",
  "amount": "1708.00",
  "reference": "Unique Reference",
  "session_id": "2319"  <!-- session id obtained from detail fetch API -->
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
  "credits_consumed": 1205.0,
  "credits_available": 9999553668.38,
  "id": 36223
}
</code></pre>

**Fields:**

- **status**: Indicates whether the API call was successful (`true`).
- **state**: The state of the transaction (`Success`).
- **message**: A message indicating the result of the transaction (`Successfully Completed Transaction`).
- **extra_data**: Any additional data related to the transaction.
- **detail**: Additional details about the payment, including a confirmation message (`Success`).
- **credits_consumed**: The total credits consumed for this transaction.
- **credits_available**: The total credits available after this transaction.
- **id**: The unique ID associated with the transaction.

