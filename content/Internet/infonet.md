# Infonet Communication API

## Overview
The Infonet Communication API enables users to process communication service transactions. By sending a POST request with the required parameters, users can manage their communication services effectively. The API provides a status update on the transaction and the remaining credits.

## API Details

- **Type**: Single Step API  
- **Test URL**: [{{base_url}}/api/use/infonet-communication/](http://service.khalti.com/api/use/royal-network/)  
- **Method**: POST  

### Service Parameters

To make a request, send the following JSON object in the body of your POST request:

<pre><code class="json">
{
    "token": "token",
    "username": "Username, eg: khaltiUser",
    "number": "9818766122",
    "amount": 100,  // Minimum Amount 100, Max: 50,000
    "address": "kathmandu",
    "reference": "infonetcommunication1"
}
</code></pre>

### Response Format

Upon a successful request, the API will return a response in the following format:

<pre><code class="json">
{
    "status": true,
    "id": 1259,
    "credits_available": 9400.0,
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

The Infonet Communication API streamlines the process of managing communication services, providing users with essential updates and ensuring efficient transaction handling.
