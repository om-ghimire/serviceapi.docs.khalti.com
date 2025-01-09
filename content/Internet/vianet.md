# Vianet Deprecated

> **Note:** Please ensure to follow the latest API in the Vianet documentation. [Click here](/Internet/vianet-new/) for more details.


### Overview

The Vianet API consists of two primary endpoints for interacting with the service:

1. **User Details Endpoint**: Retrieves details about a specific customer, including their billing information.
2. **Payment Endpoint**: Commits a payment based on the details retrieved from the first step.

### User Details

**URL:** `{{base_url}}/api/servicegroup/details/vianet/`

**Service Params:**

<pre><code class="json">
{
  "token": "token-provided",
  "customer_id": "CustomerId provided by vianet, e.g., 10619"
}
</code></pre>

**Regex:**

<pre><code class="json">
[
  {
    "name": "Customer ID",
    "slug": "",
    "pattern": "([a-zA-Z0-9_]+)",
    "error_message": "Invalid Customer Id"
  }
]
</code></pre>

**Example:**




### **Response:**

#### **Success**

<pre><code class="json">
{
  "status": true,
  "bills": [
    {
      "payment_id": "378197",
      "bill_date": "2017-09-08",
      "service_details": "FiberNet Home Rush (1 year)",
      "service_name": "serv9099",
      "amount": 23187.6
    }
  ],
  "session_id": 130,
  "customer_id": "9099",
  "customer_name": "Customer Name"
}
</code></pre>

#### **Error**

<pre><code class="json">
{
  "error_code": "1010",
  "message": "Validation error",
  "status": false,
  "error_data": "<json: *present for validation error(codes 1010, 1011) specifying errors corresponding to fields*>",
  "details": "*<empty for validation error, error details(string) for other errors>*"
}
</code></pre>

### Vianet Payment

**URL:** `{{base_url}}/api/servicegroup/commit/vianet/`

**Service Params:**

<pre><code class="json">
{
  "token": "token-provided",
  "session_id": "Session id as obtained in details step",
  "customer_id": "Customer Id, same as in details step",
  "payment_id": "Payment Id as obtained in details step",
  "reference": "unique reference_id"
}
</code></pre>

### **Response:**

#### **Success**

<pre><code class="json">
{
  "id": 496,
  "message": "Thank you for using our online Service.",
  "status": true,
  "state": "Success"
}
</code></pre>

#### **Error**

<pre><code class="json">
{
  "error_code": "1010",
  "message": "Validation error",
  "status": false,
  "error_data": "<json: *present for validation error(codes 1010, 1011) specifying errors corresponding to fields*>",
  "details": "*<empty for validation error, error details(string) for other errors>*"
}
</code></pre>
