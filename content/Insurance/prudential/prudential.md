# 11.19. Prudential Insurance

**Type**: Multi Step API

## 1. Get Branches API

**Request URL**: {{base_url}}/api/servicegroup/getpackages/prudential-insurance/

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
  "token": "token"
}
</code></pre>

**Response**:

<pre><code class="json">
{
    "status": true,
    "detail": {
        "branches": [
            {
                "branch_name": "Kathmandu",
                "id": 1
            },
            {
                "branch_name": "Birgunj",
                "id": 2
            }
        ]
    }
}
</code></pre>

## 2. Payment API

**Request URL**: {{base_url}}/api/use/prudential-insurance/

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
  "token": "<token>",
  "issue_branch": "Kathmandu",   // branches fetched from get branch API
  "customer_name": "Babu rao",
  "mobile_number": "9818822421",
  "email": "baburao@gmail.com",
  "debit_note_or_bill_number": "123456",
  "amount": "amount",
  "reference": "unique-reference"
}
</code></pre>

**Response**:

<pre><code class="json">
{
    "status": true,
    "state": "Queued",
    "detail": "Transaction Queued",
    "message": "Your operation is in queue.",
    "credits_consumed": 1200.0,
    "credits_available": 9999611980.48,
    "extra_data": {
        "issue_branch": "Kathmandu",
        "customer_name": "Babu rao",
        "mobile_number": "9818822421",
        "email": "baburao@gmail.com",
        "debit_note_or_bill_number": "123456"
    },
    "id": 35444
}
</code></pre>
