# East Link API

## Overview
The East Link API allows users to initiate a transaction by submitting a POST request. This API requires user authentication through a token and supports transactions with specified parameters, such as the username, mobile number, amount, and a reference. The API response indicates the status of the operation and provides information about credits available and consumed.

## API Details

- **Type**: Single Step API  
- **URL**: `{{base_url}}/api/use/eastlink/`  
- **Method**: POST  

### Service Parameters

To make a request, send the following JSON object in the body of your POST request:

<pre><code class="json">
{
    "token": "token",
    "username": "Username, eg: khaltiUser",
    "mobile_number": "9818766122",
    "amount": 100,  // Minimum Amount 100
    "reference": "eastlink1"
}
</code></pre>

### Response Format

Upon a successful request, the API will return a response in the following format:

<pre><code class="json">
{
    "status": true,
    "id": 1256,
    "credits_available": 9700.0,
    "message": "Your operation is in queue.",
    "state": "Queued",
    "credits_consumed": 100.0
}
</code></pre>

### Response Fields

- **status**: Indicates if the request was successful (true/false).
- **id**: A unique identifier for the transaction.
- **credits_available**: The remaining credits available after the transaction.
- **message**: A message indicating the state of the transaction.
- **state**: The current state of the transaction (e.g., "Queued").
- **credits_consumed**: The amount of credits used for the transaction.

## Conclusion

The East Link API is designed for easy and efficient transaction processing, providing necessary information for user account management and real-time updates on transaction status.
