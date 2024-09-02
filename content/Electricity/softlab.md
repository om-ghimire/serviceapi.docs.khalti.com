# ** SoftLab Electricity**

**Type: Multi-Step API**

### 1. **Detail Fetch API**

**Request URL:** {{base_url}}/api/servicegroup/details/softlab-electricity/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "{{token}}",
  "customer_code": "12",
  "month": "0",
  "reference": "unique_reference",
  "service_slug": "badagaun-electricity"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "customer_code": "12",
    "customer_name": "अर्जुन श्रेष्ठ (H2O Software)",
    "address": "इ.गा.पा.-3, फिस्लिङ्ग",
    "mobile_number": "",
    "current_month_dues": "0",
    "current_month_discount": "0",
    "current_month_fine": "0",
    "total_credit_sales_amount": "0",
    "total_advance_amount": "0.0000",
    "previous_dues": "2810",
    "total_dues": "2810",
    "minimum_payable_amount": "2810",
    "session_id": 207,
    "status": true
}
</code></pre>

**Fields:**

- **customer_code**: The code associated with the customer.
- **customer_name**: The name of the customer.
- **address**: The address of the customer.
- **mobile_number**: The mobile number of the customer (if available).
- **current_month_dues**: Dues for the current month.
- **current_month_discount**: Discount applied for the current month.
- **current_month_fine**: Fine for the current month.
- **total_credit_sales_amount**: Total amount from credit sales.
- **total_advance_amount**: Total advance amount paid.
- **previous_dues**: Outstanding dues from previous months.
- **total_dues**: Total amount due.
- **minimum_payable_amount**: Minimum amount that must be paid.
- **session_id**: Unique session ID for the transaction.
- **status**: Indicates if the API call was successful (`true`).

### 2. **Payment API**

**Request URL:** {{base_url}}/api/servicegroup/commit/softlab-electricity/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": "obtained from previous API",
  "amount": "obtained from previous API 'total_dues'"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "due_amount": "0",
    "detail": {
        "message": "Successful Payment",
        "due_amount": "0"
    },
    "credits_consumed": 2810.0,
    "credits_available": 98639503.46,
    "id": 107793
}
</code></pre>

**Fields:**

 
- **state**: The state of the transaction (`Success`).
- **message**: A message indicating the result of the transaction (`Successfully Completed Transaction`).
- **extra_data**: Any additional data related to the transaction (empty in this case).
- **due_amount**: The remaining amount due after payment.
- **detail**: Additional details about the payment, including:
  - **message**: A message indicating the success of the payment (`Successful Payment`).
  - **due_amount**: The remaining amount due (`0`).
- **credits_consumed**: The total credits consumed for this transaction.
- **credits_available**: The total credits available after this transaction.
- **id**: The unique ID associated with the transaction.


**Note** 

This documentation provides a clear and detailed view of how to use the SoftLab Electricity API, including the request and response structures for both the Detail Fetch API and the Payment API.
