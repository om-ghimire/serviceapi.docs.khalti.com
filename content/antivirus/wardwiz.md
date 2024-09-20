# Wardwiz Antivirus API

## Overview

The Wardwiz Antivirus API is a multi-step API designed to allow users to retrieve product details and process payments for Wardwiz antivirus products. This API includes two main endpoints: the **Wardwiz Product Detail API** for fetching product information and the **Wardwiz Product Payment API** for handling transactions.

## 1. Wardwiz Product Detail API

This endpoint retrieves a list of available Wardwiz antivirus products along with their details.

### Request

- **Request URL:** `{{base_url}}/api/products/wardwiz-antivirus/?token={{token}}`
- **Request Method:** `GET`
- **Service Params:** 

<pre><code class="json">
{
    "token": "\ Token\ "
}
</code></pre>

### Response

The response returns a JSON object indicating the status and an array of product details.

<pre><code class="json">
{
    "status": true,
    "data": [
        {
            "idx": "vUHWcYKWR952FuxyncsmiB",
            "name": "Wardwiz Basic 1 user / 1 year",
            "value": "WWB11",
            "amount": 700.0
        },
        {
            "idx": "ho4kmG3hbtFAEgTRpaHA54",
            "name": "Wardwiz Essential 1 user / 1 year",
            "value": "WWE11",
            "amount": 1300.0
        },
        {
            "idx": "Viwiy6wgTWiPxSbTMu79D9",
            "name": "Wardwiz Basic 3 user / 1 year",
            "value": "WWB31",
            "amount": 1300.0
        },
        {
            "idx": "jqF6Ttc9UZ4srB9K5QqMUG",
            "name": "Wardwiz Essential Plus 1 user / 1 year",
            "value": "WWEP11",
            "amount": 1500.0
        },
        {
            "idx": "6iTVKEQMyddNDT6apN7y8S",
            "name": "Wardwiz Essential 3 user / 1 year",
            "value": "WWE31",
            "amount": 2600.0
        },
        {
            "idx": "iAK3UrBTxHVu5tW2FcKcNS",
            "name": "Wardwiz Essential Plus 3 user / 1 year",
            "value": "WWEP31",
            "amount": 3000.0
        }
    ]
}
</code></pre>

## 2. Wardwiz Product Payment API

This endpoint processes the payment for the selected Wardwiz antivirus product.

### Request

- **Request URL:** `{{base_url}}/api/use/wardwiz-antivirus/`
- **Request Method:** `POST`
- **Service Params:**

<pre><code class="json">
{
    "value": "WWEP31",  // from detail API
    "amount": 3000,
    "reference": "\ unique identifier for each request\ ",
    "token": "\ token\ ",
    "name": "Wardwiz Essential Plus 3 user / 1 year"
}
</code></pre>

### Response

The response will indicate the transaction status and provide the PIN number along with other transaction details.

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Your Pin number is 'PinWEP1234'",
    "serial": "SerialWWEP1234",
    "pin": "PinWWEP1234",
    "credits_consumed": 3000.0,
    "credits_available": 9999771927.42,
    "id": 32303
}
</code></pre>
