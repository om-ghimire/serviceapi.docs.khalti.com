# Rapid Unique Net

**Type:** Multi Step API
This document outlines the APIs for fetching user details and processing payments for Rapid Unique Net services.
## 1. Details Fetch API

- **Request URL:** `{{url}}/api/servicegroup/details/rapid-api/`
- **Method:** POST

### Service Params

<pre><code class="json">
{
    "token": "provided token",
    "username": "username",
    "reference": "unique reference id"
}
</code></pre>

### Response

<pre><code class="json">
{
    "status": true,
    "details": {
        "user_id": 8897,
        "name": "test ",
        "address": "test",
        "username": "test",
        "remaining_days": 30,
        "phone_number": "9801558646",
        "amount": "1000.00",
        "added_grace_days": "0",
        "package_period": "1 Month",
        "package": "FIBER-HOME-10M"
    },
    "session_id": 11686
}
</code></pre>

---

## 2. Payment API

- **Request URL:** `{{url}}/api/servicegroup/commit/rapid-api/`
- **Method:** POST

### Service Params

<pre><code class="json">
{
    "token": "\ provided token\  ",
    "amount": "\ amount from detail fetch\  ",
    "session_id": "\ session id from get details\  "
}
</code></pre>

### Response

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Recharge Successful",
    "credits_consumed": 1001.0,
    "credits_available": 9993943006.01662,
    "id": 95287
}
</code></pre>

---


