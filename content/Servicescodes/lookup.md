# **SERVICE STATUS LOOKUP API**

The **Service Status Lookup API** allows you to check the status of a transaction by providing a reference ID and token. This API is useful for tracking the state of a transaction to determine if it was successful, failed, or if there was an error.

### **Endpoint**

**URL:** {{base_url}}/api/service/status/

**Example:** {{base_url}}/api/service/status/{{token}}/{{reference}}

**METHOD:** GET

### **Request Parameters**

The request requires the following parameters:

- **token**: The token provided for authorization.
- **reference**: The unique reference ID of the transaction for which the status needs to be checked.

**Example Request:**
<pre><code class="json">
{
    "token": "ProvidedToken",
    "reference": "reference id against which status is to be checked"
}
</code></pre>

### **Responses**

#### **Success Response**

When the transaction is successful, you will receive a response with the following structure:

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "original_status": "Success",
    "details": "Successful recharge",
    "reference": "7068074f-d04f-4262-8d9b-6a171da647b5",
    "response_id": 123647,
    "amount": 10.0,
    "refunded": false,
    "refunded_amount": 0.0,
    "refunds": []
}
</code></pre>

**Fields:**
 
- **state**: The state of the transaction (`Success`).
- **original_status**: The original status of the transaction (`Success`).
- **details**: A description of the transaction status, e.g., `"Successful recharge"`.
- **reference**: The reference ID of the transaction.
- **response_id**: The unique ID associated with the response.
- **amount**: The amount involved in the transaction.
- **refunded**: Indicates if the amount was refunded (`false`).
- **refunded_amount**: The amount that was refunded.
- **refunds**: An array of refund objects, which is empty if no refunds occurred.

#### **Failed Response**

When the transaction fails, the response will look like this:

<pre><code class="json">
{
    "status": true,
    "state": "Failed",
    "original_status": "Error",
    "details": "rtii",
    "reference": "813e70aa-889b-4b4b-b4f5-ede459d15a53",
    "response_id": 123611,
    "amount": 100.0,
    "refunded": false,
    "refunded_amount": 0.0,
    "refunds": [
        {
            "created_at": "2024-07-15",
            "remarks": "rtii",
            "amount": 100.0
        }
    ]
}
</code></pre>

**Fields:**
 
- **state**: The state of the transaction (`Failed`).
- **original_status**: The original status of the transaction (`Error`).
- **details**: A description of the failure, e.g., `"rtii"`.
- **reference**: The reference ID of the transaction.
- **response_id**: The unique ID associated with the response.
- **amount**: The amount involved in the transaction.
- **refunded**: Indicates if the amount was refunded (`false`).
- **refunded_amount**: The amount that was refunded.
- **refunds**: An array of refund objects, each containing:
  - **created_at**: The date when the refund was created.
  - **remarks**: Comments about the refund.
  - **amount**: The amount of the refund.

#### **Failure Response Structure (No such Transaction at our end)**

If the reference ID is not valid, you will receive:

<pre><code class="json">
{
    "status": false,
    "error_code": "002",
    "message": "The reference sent is not a valid reference.",
    "error": "invalid_reference",
    "details": "",
    "error_data": {},
    "state": "Error"
}
</code></pre>

**Fields:**

- **status**: Indicates whether the API call was successful (`false`).  
- **error_code**: A code representing the error (`002`).
- **message**: A message explaining the error.
- **error**: The type of error (`invalid_reference`).
- **details**: Additional details about the error.
- **error_data**: An object containing additional error data.
- **state**: The state of the response (`Error`).

#### **Failure Response Structure (Transaction Exists but Failure)**

If the transaction exists but has failed, the response will be:

<pre><code class="json">
{
    "status": true,
    "state": "Failed",
    "details": "Manually Failed",
    "reference": "Reference_092233",
    "response_id": 10631926,
    "amount": 1.0
}
</code></pre>

**Fields:**

 
- **state**: The state of the transaction (`Failed`).
- **details**: A description of the failure, e.g., `"Manually Failed"`.
- **reference**: The reference ID of the transaction.
- **response_id**: The unique ID associated with the response.
- **amount**: The amount involved in the transaction.

### **NOTE**

Please refer to the `state` field in the response to determine the success or failure of the transaction, not the `status` field.
