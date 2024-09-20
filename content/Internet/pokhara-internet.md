# Pokhara Internet API

## Overview
The Pokhara Internet API allows users to submit a transaction request to purchase internet services. By sending a POST request with the required parameters, users can manage their internet subscriptions. The API provides feedback on the transaction status and available credits.

## API Details

- **Type**: Single Step API  
- **URL**: `{{base_url}}/api/use/pokhara-internet`  
- **Method**: POST  

### Service Parameters

To make a request, send the following JSON object in the body of your POST request:

<pre><code class="json">
{
    "token": "token",
    "username": "Username, eg: khaltiUser",
    "number": "9818766122",
    "amount": 100,  // Minimum Amount 100, Max: 50,000
    "address": "Amarsingh",
    "reference": "pokharainternet1"
}
</code></pre>

### Response Format

Upon a successful request, the API will return a response in the following format:

<pre><code class="json">
{
    "status": true,
    "id": 1257,
    "credits_available": 9600.0,
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

The Pokhara Internet API facilitates the purchase of internet services, ensuring users can manage their subscriptions efficiently while receiving real-time updates on transaction status.
