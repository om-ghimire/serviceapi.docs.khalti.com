# KUKL Commit Payment Details

## API Endpoint

**URL**: `{{base_url}}/api/servicegroup/commit/kukl/`

**Method**: POST

## Request

The request must include the following **body** parameters:

### Parameters:
- `token`: `{{token}}` (required)
- `session_id`: `953` (required)
- `payment_type`: `"Bill Payment"` (required)
- `amount`: `10` (required)

### Example Request Body:

<pre><code class="json">
{
  "token": "{{token}}",
  "session_id": 953,
  "payment_type": "Bill Payment",
  "amount": 10
}
</code></pre>

## Response

A successful response will return the following JSON format:

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "receipt_no": "111410781000000063"
    },
    "detail": "Success",
    "credits_consumed": 1000.0,
    "credits_available": -999.0300000000038,
    "id": 147494
}
</code></pre>
