# **State List**

1. **Queued** 
2. **Expired**. 
3. **Processing**
4. **Error** 
5. **Status Error**
6. **Success**
7. **Failed**



| **State**      | **Description**                                        | **Action Required**               |
|----------------|--------------------------------------------------------|----------------------------------|
| **Queued**     | Transaction in unconfirmed state.                      | Need to hold client amount.       |
| **Expired**    | Transaction not possible.                             | Refund client amount.            |
| **Processing** | Transaction in unconfirmed state.                     | Need to hold client amount.       |
| **Error**      | Transaction errored.                                  | Refund client amount.            |
| **Status Error** | Transaction errored.                                | Refund client amount.            |
| **Success**    | Transaction Successful.                                | Deduct client amount.            |
| **Failed**     | Transaction errored.                                  | Refund client amount.            |
