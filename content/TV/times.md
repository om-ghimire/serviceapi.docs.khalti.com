# Times API 

Below is the list of TV services under Times and their respective `service_slug`:

### **Merotv v2** : `merotv-v2`

### **Sky TV** : `sky-tv`

## Multi-Step API

### 1. Detail Fetch API

**URL:** `{{base_url}}/api/servicegroup/userlist/times/`

**METHOD:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "Account_Token",
    "reference": "Unique Id sent from your side",
    "customer_id": "Customer_ID",  // [test customer id : 1000001]
    "service_slug": "service_slug"
}
</code></pre>

**RESPONSE:**

<pre><code class="json">
{
    "customer": {
        "cuid": "1000001",
        "first_name": "KC HARI",
        "last_name": "BIKRAM",
        "status": "active"
    },
    "connection": [
        {
            "stb": "5001067801",
            "status": "active"
        },
        {
            "stb": "5001067803",
            "status": "active"
        }
    ],
    "session_id": 7106,
    "status": true
}
</code></pre>

### 2. Package Fetch API

**URL:** `{{base_url}}/api/servicegroup/details/times/`

**METHOD:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "<Account_Token>",
    "stb": "<stb from detail fetch API>",
    "session_id": "<session_id from detail fetch API>",
    "service_slug": "<service_slug>",
    "reference": "<unique reference id>"
}
</code></pre>

**RESPONSE:**

<pre><code class="json">
{
    "packages": [
        {
            "package_id": "391",
            "package_name": "SKY HD+ Monthly (MONTHLY)",
            "amount": 550
        },
        {
            "package_id": "392",
            "package_name": "FIFA WORLD CUP 2022 (MONTHLY) [AddOn]",
            "amount": 565
        }
    ],
    "session_id": 7105,
    "status": true
}
</code></pre>

### 3. Payment API

**URL:** `{{base_url}}/api/servicegroup/commit/times/`

**METHOD:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "Account_Token",
    "session_id": "session_id from detail fetch API",
    "amount": "Package Amount from package fetch API",
    "package_id": "package ID from package fetch API"
}
</code></pre>

**RESPONSE:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Success",
    "credits_consumed": 790.0,
    "credits_available": 9999378747.53,
    "id": 42353
}
</code></pre>
