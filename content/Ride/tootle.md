## **12. Ride**

### **12.1. Tootle Topup**

#### **Tootle Fetch Detail API**

**Request URL:** {{base_url}}/api/servicegroup/details/tootle/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "token provided",
  "app": "client/partner", <!-- Choose "client" for client application, "partner" for partner application -->
  "number": "registered mobile number"
}
</code></pre>

**Note:** Choose `client` for topping up the client application and `partner` for topping up the partner application.

**Regex:**

<pre><code class="json">
[
  {
    "name": "Smart Card Id",
    "slug": "",
    "pattern": "^([9][678][0-9]{8})$",
    "error_message": "Invalid ID"
  }
]
</code></pre>

**Response:**

<pre><code class="json">
{
  "product_identity": "D-31",
  "status": true,
  "gender": "Female",
  "number": "9841579738",
  "name": "Bina Laxmi Shrestha"
}
</code></pre>

**Fields:**
- **product_identity**: The unique identity of the product.
- **status**: Indicates whether the API call was successful (`true`).
- **gender**: The gender of the customer.
- **number**: The registered mobile number of the customer.
- **name**: The name of the customer.

#### **Tootle Commit API**

**Request URL:** {{base_url}}/api/servicegroup/commit/tootle/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "token provided",
  "product_identity": "obtained from detail API",
  "number": "registered mobile number",
  "amount": "amount to topup",
  "reference": "Unique reference id"
}
</code></pre>

**Response:**

<pre><code class="json">
{
  "id": 3856,
  "state": "Success",
  "extra_data": {},
  "detail": {
    "message": "Tootle topped up successfully for user Bina"
  },
  "status": true,
  "message": "Successfully Completed Transaction"
}
</code></pre>

**Fields:**
- **id**: The unique ID associated with the transaction.
- **state**: The state of the transaction (`Success`).
- **extra_data**: Any additional data related to the transaction.
- **detail**: Additional details about the top-up, including a confirmation message.
- **status**: Indicates whether the API call was successful (`true`).
- **message**: A message indicating the result of the transaction (`Successfully Completed Transaction`).

This documentation provides the details for fetching user information and processing top-ups for the Tootle service.
