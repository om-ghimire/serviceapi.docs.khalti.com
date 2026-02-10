# **WiFi Nepal V4**

**Type: Two-Step API**

### 1. **Detail Fetch API**

**Request URL:** `{{base_url}}/api/servicegroup/details/wifi-nepal-v4/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "username": "33222"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "session_id": 48250,
    "case": "advance",
    "package": {
        "id": 299,
        "name": "Festival Offer 100 Mbps/mnth"
    },
    "due_amount": 10000,
    "subscriber": {
        "name": "sajilo net",
        "phone": "1234567890",
        "address": "Jeebandan oil suppliers, NH09, Pyuthan-07",
        "subscriber_id": 218300
    },
    "status": true
}
</code></pre>

### 2. **Payment API**

**Request URL:** `{{base_url}}/api/servicegroup/commit/wifi-nepal-v4/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{token}}",
    "session_id": "{{session_id}}",
    "subscriber_id": "{{subscriber_id}}",
    "amount": 10000,
    "reference": "{{$guid}}"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Subscription paid successfully",
    "credits_consumed": 10000,
    "credits_available": "xx.xx",
    "id": 190543
}
</code></pre>

### **Important Notes:**

1. **Session ID**: Obtained from the Detail Fetch API response
2. **Amount**: Should match the `due_amount` from the Detail Fetch API response
