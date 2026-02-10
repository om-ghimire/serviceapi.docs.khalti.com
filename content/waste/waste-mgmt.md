# **Waste Management**

Please find the name of the waste management services and their respective slugs.

| Service Name | Slug |
|--------------|------|
| Clean Nepal Kathmandu | clean-nepal-kathmandu |
| Clean Nepal Surkhet | clean-nepal-surkhet |
| Action Waste Baneshwor | action-waste-baneshwor |
| Active Nepal Boudha | active-nepal-boudha |
| Creative Sarsafai | creative-sarsafai |
| Sarbakalyan Sewa Thankot | sarbakalyan-sewa-thankot |
| Nepal Batabaran Srijana | nepal-batabaran-srijana |
| Metro City Waste Management | metro-city-waste-management |
| Nepal Fulbari Waste Management | nepal-fulbari-waste-management |
| Nepal Swocha Batabaran Srijana Kendra | nepal-swocha-batabaran-srijana-kendra |
| Nepal Swocha Batabaran Samrachan Samiti | nepal-swocha-batabaran-samrachan-samiti |
| Kirtipur Fohor Bebasthapan | kirtipur-fohor-bebasthapan |
| Nepco - National Environment Pollution Control | national-environment-pollution-control |

**Type: Multi-Step API**

### 1. **Service List API**

**Request URL:** `{{base_url}}/api/servicegroup/servicelist/waste-management/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{token}}"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "services": [
      
        {
            "service_name": "Clean Nepal Kathmandu",
            "service_slug": "clean-nepal-kathmandu"
        },
        {
            "service_name": "Koteshwor Waste Management",
            "service_slug": "koteshwor-waste-management"
        }
    ],
    "status": true
}
</code></pre>

### 2. **Detail Fetch API**

**Request URL:** `{{base_url}}/api/servicegroup/details/waste-management/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "card_no": "customer_card_number",
    "service_slug": "clean-nepal-kathmandu",
    "mobile_no": "customer_mobile_number"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "customer_id": 116,
    "customer_name": "Chiri Mai Maharjan",
    "card_no": "1",
    "mobile_no": "9800000000",
    "per_month_rate": 450.0,
    "past_payments": [
        {
            "year_from": 2081,
            "year_to": 2081,
            "month_from": 8,
            "month_to": 9,
            "total_paid": 900.0,
            "order_key": "18864"
        },
        {
            "year_from": 2081,
            "year_to": 2081,
            "month_from": 10,
            "month_to": 12,
            "total_paid": 1350.0,
            "order_key": "26303"
        },
        {
            "year_from": 2082,
            "year_to": 2082,
            "month_from": 1,
            "month_to": 1,
            "total_paid": 450.0,
            "order_key": "30497"
        }
    ],
    "year_list": [
        {
            "label": "2076",
            "value": 2076
        },
        {
            "label": "2077",
            "value": 2077
        },
        {
            "label": "2078",
            "value": 2078
        },
        {
            "label": "2079",
            "value": 2079
        },
        {
            "label": "2080",
            "value": 2080
        },
        {
            "label": "2081",
            "value": 2081
        },
        {
            "label": "2082",
            "value": 2082
        },
        {
            "label": "2083",
            "value": 2083
        }
    ],
    "session_id": 954,
    "status": true
}
</code></pre>

### 3. **Calculate API**

**Request URL:** `{{base_url}}/api/servicegroup/calculate/waste-management/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{token}}",
    "session_id": 954,
    "month_from": 4,
    "month_to": 5,
    "year_from": 2081,
    "year_to": 2081
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "detail": {
        "total_amount": 900.0,
        "total_month": 2.0,
        "rate": 450.0
    }
}
</code></pre>

### 4. **Payment API**

**Request URL:** `{{base_url}}/api/servicegroup/commit/waste-management/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "{{token}}",
    "session_id": 954,
    "amount": 900.0,
    "reference": "{{$guid}}",
    "service_slug": "clean-nepal-kathmandu"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Transaction Success",
    "credits_consumed": 900.0,
    "credits_available": xxxx,
    "id": 180108
}
</code></pre>

### **Important Notes:**

1. **Session ID**: Obtained from Detail Fetch API response, required for Calculate and Payment APIs
2. **Service Slug**: Select from the Service List API response or use slugs from the table above
3. **Card No & Mobile No**: Required for Detail Fetch API to retrieve customer information
4. **Date Parameters**: Use Nepali calendar months (1-12) and years from the `year_list` in Detail Fetch API
5. **Amount**: Should match the `total_amount` from Calculate API response
6. **Per Month Rate**: Available in Detail Fetch API response for reference