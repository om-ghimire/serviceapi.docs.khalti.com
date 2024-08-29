# Transaction Processing Guide

## State List

1. **Queued**  
   - **Description**: Transaction in unconfirmed state.  
   - **Action**: Need to hold client amount.

2. **Expired**  
   - **Description**: Transaction not possible.  
   - **Action**: Refund client amount.

3. **Processing**  
   - **Description**: Transaction in unconfirmed state.  
   - **Action**: Need to hold client amount.

4. **Error**  
   - **Description**: Transaction errored.  
   - **Action**: Refund client amount.

5. **Status Error**  
   - **Description**: Transaction errored.  
   - **Action**: Refund client amount.

6. **Success**  
   - **Description**: Transaction Successful.  
   - **Action**: Deduct client amount.

7. **Failed**  
   - **Description**: Transaction Errored.  
   - **Action**: Refund client amount.

## Response Status Handling

- **status**: Check the `status` key in the response:
  - **True**: The request is submitted successfully.
  - **False**: There is an issue with the request. Please fix your request.

- **State Handling**:
  - If the state is **Queued** or **Processing**, you will receive the final status of the transaction in the DLR callback later.
  - If the state is **Success**, **Failed**, or **Error**, take action based on the state immediately. No need to wait for DLR.

## DLR Sample

<pre><code class="json">
Content-Type: multipart/form-data
{
    "reference": "Unique id sent by you",
    "amount": "amount",
    "status": "status",
    "detail": "detail regarding the service",
    "response_id": "response id from ntc/ncell or other provider"
}
</code></pre>


**NOTE ON FIELD VALIDATION** : Enforce a length of 50 alphanumeric characters as a default validation unless explicitly mentioned.

## **Service Layer State**

| HTTP Response Code | Status | act | Remarks |
| :---- | :---- | :---- | :---- |
| 200 | Success | Check state in response data and proceed based on state | Check state in response data and proceed based on state  |
| 400 | Error | Hold | Need to check the transaction state to proceed.  |
| 404 | Error | Refund | Service not found |
| \>= 500 | Server error  | Hold | Server is failed to provide the response **Third Party should hold the transaction and call lookup api after at least 5 mins to get transaction status to proceed further**  |
| Other any status code or No status code received | Timeout | Hold | Server is failed to provide the response **Third Party should hold the transaction and call lookup api after at least 5 mins to get transaction status to proceed further** |




| State | Act | Description |
| :---- | :---- | :---- |
| Success | Process | Transaction Successful.  **Deduct Client amount**  |
| Queued | Hold | Transaction in pending state.  **Third Party should hold the transaction and call lookup api after at least after 5 mins to get transaction status to proceed further** |
| Processing | Hold | Transaction in pending state.  **Third Party should hold the transaction and call lookup api after atleast 5 mins to get transaction status to proceed further** |
| Expired | Refund | Transaction not possible.  **Refund client amount**  |
| Error | Refund | Transaction error.  **Refund Client amount** |
| Failed | Refund | Transaction Error.  **Refund Client amount.** |
| Any other state or no state received | Hold | Server is failed the provide the response **Third Party should hold the transaction and call lookup api after atleast 5 mins to get transaction status to proceed further** |
| Timeout  | Hold | **Third Party should hold the transaction and call lookup api after atleast 5 mins to get transaction status to proceed further** |
