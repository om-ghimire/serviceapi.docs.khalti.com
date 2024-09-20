# Eset Antivirus API

## Overview

The Eset Antivirus API is a multi-step API that allows users to retrieve product details and make purchases of antivirus solutions. It consists of two primary endpoints: the **Get Detail API** for fetching product information and the **Purchase API** for completing transactions.

## 1. Get Detail API

This endpoint retrieves the available Eset antivirus products along with their details.

### Request

- **Request URL:** `{{base_url}}/api/products/eset-antivirus/`
- **Request Method:** `GET`
- **Service Params:** 
  
<pre><code class="json">
{
    "token": "\ token\ "
}
</code></pre>

### Response

The response will return a JSON object containing the status and an array of product details.

<pre><code class="json">
{
    "status": true,
    "data": [
        {
            "idx": "znR2fUJHM8YZ4GFh43fZKC",
            "name": "eset Mobile Security",
            "value": "EMS",
            "amount": 900.0
        },
        {
            "idx": "BnF4bGdc7BAzFoA2tSqQGK",
            "name": "eset Antivirus 1user 1year",
            "value": "EA11",
            "amount": 900.0
        },
        {
            "idx": "CWcNh6qYEorY4H4kpcqUPk",
            "name": "eset Antivirus 3user 1year",
            "value": "EA31",
            "amount": 1800.0
        },
        {
            "idx": "T6USwHFwNcyGLpr5kMqRbU",
            "name": "eset Antivirus 1user 3 year",
            "value": "EA13",
            "amount": 2000.0
        },
        {
            "idx": "WgoBqQAxF7TwEzzMYqJNsP",
            "name": "eset Antivirus 5user 1 year",
            "value": "EA51",
            "amount": 2800.0
        },
        {
            "idx": "cXSgMtPzCwU2uShVeE2FbJ",
            "name": "eset Internet Security 1user 1year",
            "value": "EIS11",
            "amount": 1800.0
        },
        {
            "idx": "Qw7dXmfNxVTBZWXgaCAABj",
            "name": "eset Internet Security 1user 3year",
            "value": "EIS13",
            "amount": 3800.0
        },
        {
            "idx": "gSJoYy3PZMqHob8iHGe5Z6",
            "name": "eset Internet Security 3user 1year",
            "value": "EIS31",
            "amount": 3600.0
        },
        {
            "idx": "ZBCh49vMaXCzuVzTJjzpV6",
            "name": "eset Internet Security 5user 1year",
            "value": "EIS51",
            "amount": 5000.0
        },
        {
            "idx": "hJS2GYFu2B5ELdsKfTXcwk",
            "name": "eset Smart Security Premium 1user 1year",
            "value": "ESSP11",
            "amount": 4000.0
        },
        {
            "idx": "YDhbheLfWBmqSFdmxHPeqj",
            "name": "eset Smart Security Premium 3user 1year",
            "value": "ESSP31",
            "amount": 5500.0
        },
        {
            "idx": "B7NiUMEoec4s9Pk9cUYCxA",
            "name": "eset Smart Security Premium 5user 1 year",
            "value": "ESSP51",
            "amount": 6500.0
        }
    ]
}
</code></pre>

## 2. Purchase API

This endpoint allows users to purchase selected Eset antivirus products.

### Request

- **Request URL:** `{{base_url}}/api/use/eset-antivirus/`
- **Request Method:** `POST`
- **Service Params:**

<pre><code class="json">
{
    "token": "\ token\ ",
    "reference": "\ unique identifier for each request\ ",
    "amount": 6500,
    "value": "ESSP51"
}
</code></pre>

### Response

The response will confirm the transaction and provide a PIN number along with other transaction details.

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Your Pin number is '2098'",
    "serial": "1098",
    "pin": "2098",
    "credits_consumed": 6500.0,
    "credits_available": 106407713.395,
    "id": 9733
}
</code></pre>
