# **21. Cable Car** 

Please find the name of the cable car and their respective slug.

- **Manakamana Cable Car**: manakamana-cable-car  
- **Annapurna Cable Car**: annapurna-cable-car

**Type: Multi-Step API**

### 1. **Detail Fetch API**

**Request URL:** {{base_url}}/api/servicegroup/details/cable-car/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "unique reference",
    "service": "slug",
    "trip_type": "One Way/Two Way"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "trips": [
        {
            "trip_type": "One Way",
            "passenger_type": "Normal",
            "price": 395.0,
            "vat": 45.44,
            "lc": 0.0,
            "passenger_type_desc": "Normal"
        },
        {
            "trip_type": "One Way",
            "passenger_type": "Child",
            "price": 240.0,
            "vat": 27.61,
            "lc": 0.0,
            "passenger_type_desc": "Child"
        },
        {
            "trip_type": "One Way",
            "passenger_type": "Student",
            "price": 300.0,
            "vat": 34.51,
            "lc": 0.0,
            "passenger_type_desc": "Student"
        },
        {
            "trip_type": "One Way",
            "passenger_type": "Elderly",
            "price": 275.0,
            "vat": 31.64,
            "lc": 0.0,
            "passenger_type_desc": "Elderly"
        },
        {
            "trip_type": "One Way",
            "passenger_type": "Diff-Able",
            "price": 190.0,
            "vat": 21.86,
            "lc": 0.0,
            "passenger_type_desc": "Differently Able"
        },
        {
            "trip_type": "One Way",
            "passenger_type": "Indian",
            "price": 496.0,
            "vat": 57.06,
            "lc": 0.0,
            "passenger_type_desc": "Indian Normal"
        },
        {
            "trip_type": "One Way",
            "passenger_type": "Indian-CH",
            "price": 320.0,
            "vat": 36.81,
            "lc": 0.0,
            "passenger_type_desc": "Indian Child"
        }
    ],
    "session_id": 3971,
    "status": true
}
</code></pre>

### 2. **Payment API**

**Request URL:** {{base_url}}/api/commit/cable-car/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "unique reference",
    "session_id": "session_id", // obtained from Detail Fetch API
    "trip_type": "One Way/Two Way", // obtained from Detail Fetch API
    "contact_name": "contact_name",
    "mobile_number": "mobile_number",
    "tickets": [
        {
            "passenger_type": "passenger_type", // obtained from Detail Fetch API
            "passenger_count": passenger_count
        }
    ],
    "amount": "amount" // obtained from Detail Fetch API
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {
        "transaction_id": "443",
        "bill_number": "T4767711565"
    },
    "detail": "Payment Successful",
    "credits_consumed": 395.0,
    "credits_available": "xxxxx",
    "id": 115044
}
</code></pre>

### 3. **Ticket API**

**Request URL:** {{base_url}}/api/commit/downloadticket/cable-car/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{token}}",
    "session_id": 3969, // obtained from Detail Fetch API
    "service": "slug",
    "base64": true
}
</code></pre>


