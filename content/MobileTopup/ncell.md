# Ncell API Documentation

## Overview

The Ncell API endpoint allows you to perform a single-step transaction. This API requires a POST request and provides information about the success or failure of the transaction.

**URL:** [{{base_url}}/api/use/ncell/](https://services.khalti.com/api/use/ncell/)  
**Type:** Single Step API  
**Method:** POST

## Request Parameters

The following parameters are required in the POST request:

- **number:** 10-digit mobile number
- **token:** Authentication token
- **reference:** Unique reference for the transaction
- **amount:** Amount between 50 to 25000

### Valid Amounts

- From 50 to 5000

## Request Example



<pre><code class="json">
{
    "token": "Token Provided",
    "reference": "unique-reference",
    "amount": "amount",
    "number": "number(eg:9801234567)"
}
</code></pre>