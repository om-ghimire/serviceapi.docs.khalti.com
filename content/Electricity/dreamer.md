# **20.3 Dreamer Electricity**

**Below is the list of Life Insurances under Dreamer Electricity and their service_slug:**

1. ##### **Khamari Khola Electricity**: khamari-khola-electricity

   … others to be added

**Type: Multi-Step API**

### 1. **Detail Fetch API**

**Request URL:** {{base_url}}/api/servicegroup/details/dreamer-electricity/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "{{token}}",
  "customer_code": "01-1",
  "reference": "unique_reference",
  "service_slug": "service_slug"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "consumer_id": 13,
    "consumer_no": "01-1",
    "consumer_name": "01-1 Bryan Hamal",
    "address": "Tole",
    "total_payable_amount": 180,
    "total_discount": 20,
    "total_penalty": 0,
    "total_bill_amount": 200,
    "due_bills": [
        {
            "bill_id": 58,
            "bill_year": "2078",
            "bill_month": "Baishak",
            "bill_amount": 200,
            "penalty": 0,
            "discount": 20,
            "no_of_days": 2,
            "total_amount": 180
        }
    ],
    "session_id": 119,
    "status": true
}
</code></pre>

**Fields:**

- **consumer_id**: The unique ID of the consumer.
- **consumer_no**: The consumer number.
- **consumer_name**: The name associated with the consumer number.
- **address**: The address of the consumer.
- **total_payable_amount**: The total amount payable after discounts and penalties.
- **total_discount**: The total discount applied.
- **total_penalty**: The total penalty incurred.
- **total_bill_amount**: The total amount of the bill before discounts and penalties.
- **due_bills**: An array containing details of the due bills, including:
  - **bill_id**: The unique ID of the bill.
  - **bill_year**: The year of the bill.
  - **bill_month**: The month of the bill.
  - **bill_amount**: The amount of the bill.
  - **penalty**: The penalty amount.
  - **discount**: The discount applied.
  - **no_of_days**: The number of days overdue.
  - **total_amount**: The total amount due after applying the penalty and discount.
- **session_id**: The unique session ID for the transaction.
 

### 2. **Payment API**

**Request URL:** {{base_url}}/api/servicegroup/commit/dreamer-electricity/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "unique_reference",
  "session_id": "obtained from previous API",
  "amount": "obtained from previous API 'total_payable_amount'"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "receipt_no": 2
    },
    "detail": "Payment Successful",
    "credits_consumed": 180.0,
    "credits_available": "xxxxx",
    "id": 107743
}
</code></pre>

**Fields:**

 
- **state**: The state of the transaction (`Success`).
- **message**: A message indicating the result of the transaction (`Successfully Completed Transaction`).
- **extra_data**: Any additional data related to the transaction, including:
  - **receipt_no**: The receipt number for the transaction.
- **detail**: Additional details about the payment, including:
  - **message**: A message indicating the success of the payment (`Payment Successful`).
- **credits_consumed**: The total credits consumed for this transaction.
- **credits_available**: The total credits available after this transaction.
- **id**: The unique ID associated with the transaction.



*Note This*

This documentation outlines the request and response formats for the Dreamer Electricity API, including details for both the Detail Fetch API and the Payment API.
