# Dishhome FIFA Recharge

This service allows users to purchase the Dishhome FIFA Recharge package. After a successful payment, the FIFA World Cup channels will be activated on the user's TV.

## Success Message Suggestion

- FIFA World Cup package has been activated for ID `{request_id}`. Please wait up to 30 minutes if the channels do not appear on your TV.

---


## Integration Flow

1. Call Detail Fetch API using CAS ID / Customer ID / MAC ID.
2. Receive `session_id`, `amount`, and `device_identifiers`.
3. Select a device identifier.
4. Call Payment API with the exact amount and selected device ID.
5. FIFA package gets activated after successful payment.

---

## Validation Rules

- Customer expiry date must be greater than or equal to `2026-07-21`.
- Recharge amount must exactly match the fetched amount.

---

## 1. Detail Fetch

This API fetches customer details required for the FIFA recharge process.

The `request_id` can be: Customer ID, CAS ID,MAC ID (for IPTV users)

These identifiers are provided by Dishhome.

**POST**  
`{{base_url}}/api/servicegroup/details/dishhome-fifa-recharge/`

### Request Body

<pre><code class="json">
{
  "token": "{your token}",
  "reference": "{unique identifier}",
  "request_id": "13859499"
}
</code></pre>

### Response


<pre><code class="json">
{
  "session_id": 45184,
  "expiry_date": "2027-10-05T10:45:00",
  "customer_name": "DTH TEST",
  "status": true,
  "customer_status": "Prepaid On",
  "amount": 999.0,
  "device_identifiers": [
    {
      "label": "DTH - 888279618D44",
      "value": "888279618D44"
    },
    {
      "label": "STB - 71909749799",
      "value": "71909749799"
    },
    {
      "label": "STB - 71909750524",
      "value": "71909750524"
    },
    {
      "label": "STB - 71907915533",
      "value": "71907915533"
    }
  ]
}
</code></pre>

### Notes

- `session_id` will be required during payment.
- `amount` should be used as the exact payment amount.
- `device_identifiers` contains the available device IDs for recharge.

---

## 2. Payment

This API processes the payment and activates the FIFA channels on the selected device.

**POST**  
`{{base_url}}/api/servicegroup/commit/dishhome-fifa-recharge/`


### Request Body

<pre><code class="json">
{
  "token": "{Your token}",
  "reference": "{unique identifier}",
  "session_id": "{{session_id}}",
  "amount": 999.0,
  "contact_number": "9860848045",
  "payment_request_id": "888279618D44"
}
</code></pre>

### Field Description

| Field | Description |
|---|---|
| `session_id` | Received from the Detail Fetch API response |
| `amount` | Exact amount received from the Detail Fetch API |
| `payment_request_id` | One of the `value` fields from `device_identifiers` |
| `contact_number` | Customer mobile number |

### Response

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {},
  "detail": {
    "message": "Successful"
  },
  "credits_consumed": 999.0,
  "credits_available": 99986842144.7998,
  "id": 177379
}
</code></pre>

---