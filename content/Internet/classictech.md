# Classic Tech

### Overview

The Classic Tech API provides two main endpoints to manage user details and process payments:

1. **User Detail API**: Retrieves details about a user's available plans and session information.
2. **Payment API**: Commits a payment using the details obtained from the User Detail API.

### User Detail API

**URL:** `{{base_url}}/api/servicegroup/details/classictech-isp/`

**METHOD:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "provided_token",
  "reference": "unique reference id",
  "username": "classitech_username, e.g., ctdeveloper"
}
</code></pre>

**Response:**

#### **Success**

<pre><code class="json">
{
  "status": true,
  "token": "d95f1f947faf32d131c01a6e77d75938",
  "session_id": 8,
  "available_plans": [
    {
      "package": "Classic-30Mbps",
      "duration": "1",
      "amount": 1695
    },
    {
      "package": "Classic-30Mbps",
      "duration": "3",
      "amount": 4403.61
    },
    {
      "package": "Classic-30Mbps",
      "duration": "15",
      "amount": 12430
    }
  ]
}
</code></pre>

### Payment API

**URL:** `{{base_url}}/api/servicegroup/commit/classictech-isp/`

**METHOD:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "<provided_token>",
  "session_id": "<session id from detail step>",
  "plan_id": "<plan_id from detail step>"
}
</code></pre>

**Sample Response:**

#### **Success Response**
<pre><code class="json">
{
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {},
  "status": true,
  "id": 2420
}
</code></pre>
