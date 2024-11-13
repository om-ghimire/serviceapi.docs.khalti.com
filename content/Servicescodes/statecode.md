

# State List

| **State**      | **Description**                                        | **Action Required**               |
|----------------|--------------------------------------------------------|----------------------------------|
| **Queued**     | Transaction in unconfirmed state.                      | Need to hold client amount.       |
| **Expired**    | Transaction not possible.                             | Refund client amount.            |
| **Processing** | Transaction in unconfirmed state.                     | Need to hold client amount.       |
| **Error**      | Transaction errored.                                  | Refund client amount.            |
| **Status Error** | Transaction errored.                                | Refund client amount.            |
| **Success**    | Transaction Successful.                                | Deduct client amount.            |
| **Failed**     | Transaction errored.                                  | Refund client amount.            |


## Response Status Handling

- **status**: Check the `status` key in the response:
  - **True**: The request is submitted successfully.
  - **False**: There is an issue with the request. Please fix your request.

- **State Handling**:
  - If the state is **Queued** or **Processing**, you will receive the final status of the transaction in the DLR callback later.
  - If the state is **Success**, **Failed**, or **Error**, take action based on the state immediately. No need to wait for DLR.