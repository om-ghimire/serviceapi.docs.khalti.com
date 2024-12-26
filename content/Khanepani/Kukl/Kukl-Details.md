# KUKL Khanepani Customer Details Fetch

## API Endpoint

**URL**: `{{base_url}}/api/servicegroup/details/kukl/`

**Method**: POST

## Request

The request must include the following **body** parameters:

### Important Note:
- If `customer_code` is provided, the `connection_no` should **not** be sent.
- If `connection_no` is provided, the `customer_code` should **not** be sent.
- One of these fields, **customer_code** or **connection_no**, is **required** but not both.

### Example Request Body:

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}",
  "counter": "1114:test-kukl",
  "customer_code": "1114003014"
}
</code></pre>

or

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "{{$guid}}",
  "counter": "1114:test-kukl",
  "connection_no": "9352"
}
</code></pre>

## Response

A successful response will return the following JSON format:

<pre><code class="json">
{
    "status": true,
    "customer_code": "1114013895",
    "connection_no": "123321323",
    "customer_name": "RABI MAN MANNANDHAR",
    "address": "DHOKA BAHAL",
    "area_no": "27-03-25GHA",
    "bill_month": "207809",
    "current_month_fine": 0,
    "total_advance_amount": 0,
    "amount": 141.85,
    "unapproved_adjustment": 123.12,
    "unapproved_penalty": 23.45,
    "minimum_payable_amount": 141.85,
    "session_id": 2630
}
</code></pre>

