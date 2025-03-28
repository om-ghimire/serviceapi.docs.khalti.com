# Nepal Telecom (NTC) API

The Nepal Telecom API endpoint allows you to perform a single-step transaction. This API requires a POST request and provides information about the success or failure of the transaction.

## API Details

- **URL:** ``{{base_url}}/api/use/ntc/``
- **Type:** Single Step API
- **Request Type:** POST

## Parameters

- **number**: 10-digit mobile number (NT Prepaid, NT Postpaid, NT CDMA Prepaid & Postpaid)
- **token**: Authentication token
- **reference**: Unique reference identifier
- **amount**: Between 10 to 25,000

## Request Format

The request body should be in JSON format:

<pre><code class="json">
{
    "token": "Token Provided",
    "reference": "unique-reference",
    "amount": "amount",
    "number": "number"
}
</code></pre>

## Success Response Format
    
<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Transaction successful",
    "credits_consumed": 1000,
    "credits_available": 1e+24,
    "id": 163
}
</code></pre>

