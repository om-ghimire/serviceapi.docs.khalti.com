# **Sanima Insurance API**

**Note**: Reliance and Sanima Life Insurance have merged. Please use the Reliance Life Insurance API.

**Type**: Multi Step API

## Overview

The Reliance Insurance API facilitates interactions with Reliance Insurance services, including retrieving user details and processing payments. The API involves two primary steps:

1. **USER DETAIL API**: Fetches policy details and user information based on the provided policy number and date of birth.
   
2. **Payment API**: Handles the payment process for the insurance policy using the information retrieved from the USER DETAIL API.

## USER DETAIL API

**Request URL**: {{base_url}}/api/servicegroup/details/reliance-insurance/

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
  "token": "provided_token",
  "policy_no": "301000003781",
  "dob": "YYYY-MM-DD"
}
</code></pre>

**Sample Response**:

**Success**:

<pre><code class="json">
{
  "paymode": "Yearly",
  "transaction_id": "100373",
  "product_name": "Endowment Assurance Cum Whole Life Policy",
  "customer_id": "301000000277",
  "next_due_date": "2019-02-20",
  "status": true,
  "invoice_number": "",
  "amount": "43845.00",
  "customer_name": "HARI CHANDRA YADAV",
  "address": "Auradi",
  "fine_amount": "949.0000"
}
</code></pre>

**Overview**: 
The USER DETAIL API allows you to fetch detailed information about an insurance policy using the policy number and date of birth. It provides details such as the product name, next due date, amount payable, and customer information.

## Payment API

**Request URL**: {{base_url}}/api/servicegroup/commit/reliance-insurance/

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
  "token": "<provided_token>",
  "amount": "<amount_to_be_paid_from_detail_step>",
  "policy_no": "<policy_no_for_which_payment_is_being_made>",
  "transaction_id": "<transaction_id_from_details_step>",
  "reference": "<unique_reference_identifier>"
}
</code></pre>

**Sample Response**:

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {
    "customer_id": "101000000008",
    "customer_name": "BIBEK KUMAR DEV",
    "next_due_date": "11/04/2019",
    "product_name": "Child Assurance Plan",
    "fine_amount": "0.00",
    "invoice_number": "RP001",
    "transaction_id": "100051"
  },
  "detail": {
    "customer_id": "101000000008",
    "customer_name": "BIBEK KUMAR DEV",
    "next_due_date": "11/04/2019",
    "product_name": "Child Assurance Plan",
    "fine_amount": "0.00",
    "invoice_number": "RP001",
    "transaction_id": "100051"
  },
  "credits_consumed": 43845.0,
  "credits_available": 9993994136.51662,
  "id": 93762
}
</code></pre>

**Overview**: 
The Payment API processes payments for the insurance policy. It requires details such as the policy number, transaction ID, amount to be paid, and a unique reference identifier. Upon successful payment, it returns information about the transaction, including customer details and payment status.
