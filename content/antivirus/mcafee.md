# McAfee Antivirus API

## Overview

The McAfee Antivirus API is a multi-step API designed for users to access product details and process payments for McAfee antivirus products. This API consists of two main endpoints: the **Product Detail API** for retrieving product information and the **Product Payment API** for handling purchases.

## 1. Product Detail API

This endpoint retrieves a list of available McAfee antivirus products along with their details.

### Request

- **Request URL:** `{{base_url}}/api/products/mcafee-antivirus/?token={{token}}`
- **Request Method:** `GET`
- **Service Params:** 

<pre><code class="json">
{
    "token": "Token"
}
</code></pre>

### Response

The response returns a JSON object indicating the status and an array of product details.

<pre><code class="json">
{
    "status": true,
    "data": [
        {
            "idx": "T8EBDkFt8VenB9ZJMKt7YS",
            "name": "Mcafee Antivirus 1PC / 1 Year",
            "value": "MA-1P-1Y",
            "amount": 700.0
        },
        {
            "idx": "FbZxh4eBziQFxLHT73oR7A",
            "name": "Mcafee Mobile Security 1 Phone / 1 Year",
            "value": "MMS-1P-1Y",
            "amount": 700.0
        },
        {
            "idx": "9jniFusARPdsYkMGarpRDc",
            "name": "Mcafee Internet Security 1 Device / 1 Year",
            "value": "MIS-1D-1Y",
            "amount": 1350.0
        },
        {
            "idx": "nouBj2b7CZuXcipSzf6zsi",
            "name": "Mcafee Antivirus 3PC / 1 Year",
            "value": "MA-3P-1Y",
            "amount": 1500.0
        },
        {
            "idx": "gWd9NT4YR6HXLNrCTqPHdV",
            "name": "Mcafee Total Protection 1 Device / 1 Year",
            "value": "MTP-1D-1Y",
            "amount": 1550.0
        },
        {
            "idx": "yGz5AJzv3nCjDCt33gw4sW",
            "name": "Mcafee Internet Security 3 Device / 1 Year",
            "value": "MIS-3D-1Y",
            "amount": 2500.0
        },
        {
            "idx": "Ussq53tPpygK3795XKnU3D",
            "name": "Mcafee Total Protection 3 Device / 1 Year",
            "value": "MTP-3D-1Y",
            "amount": 3150.0
        }
    ]
}
</code></pre>

## 2. Product Payment API

This endpoint processes the payment for the selected McAfee antivirus product.

### Request

- **Request URL:** `{{base_url}}/api/use/mcafee-antivirus/`
- **Request Method:** `POST`
- **Service Params:**

<pre><code class="json">
{
    "value": "MA-1P-1Y",  // from detail API
    "amount": 700,
    "reference": "unique identifier for each request",
    "token": "token",
    "name": "Mcafee Antivirus 1PC / 1 Year"
}
</code></pre>

### Response

The response will indicate the transaction status and provide the PIN number along with other transaction details.

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Your Pin number is '123545'",
    "serial": "123545",
    "pin": "123545",
    "credits_consumed": 700.0,
    "credits_available": 9999740618.32,
    "id": 33415
}
</code></pre>
