# Service Charges API

This API allows you to create service charges for a specific service by providing relevant details such as the token, service identifier, and amount.

---

### Endpoint
**URL**: `{{base_url}}/api/account/service-charges/`  
**Method**: `GET`

---

### Request Body

To create a service charge, you must send a JSON object in the body of the request. The required fields are:

- `token`: The authentication token (string).
- `service_slug`: A unique identifier for the service (string).
- `amount`: The amount on which the service charge is calculated (numeric).

Example request body:

<pre><code class="json">
{
    "token": "your_auth_token",
    "service_slug": "example_service_slug",
    "amount": 500
}
</code></pre>

---

### Response

If the request is successful, the response will include a status and the calculated service charge details.

Example response:

<pre><code class="json">
{
    "status": true,
    "details": {
        "amount": 500,
        "service_charge": 5.0
    }
}
</code></pre>


