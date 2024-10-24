# **Khanepani**

### Khanepani Counters

**URL:** `{{base_url}}/api/servicegroup/counters/khanepani/`  
**Method:** ``POST``  

**Request Body:**
<pre><code class="json">
{
    "token": "token"
}
</code></pre>

**Response:**
<pre><code class="json">
{
    "counters": [
        {
            "name": "Sandhikharka",
            "value": "268:sandhikharka-khanepani"
        },
        {
            "name": "Itahari",
            "value": "3:itahari-khanepani"
        }
    ],
    "status": true
}
</code></pre>

**Description:**  
Retrieve a list of available Khanepani counters.

### Khanepani Details

**URL:** `{{base_url}}/api/servicegroup/details/khanepani/`  
**Method:** ``POST``  

**Request Body:**
<pre><code class="json">
{
    "month_id": "number (1 to 12 inclusive)",
    "customer_code": "numeric value, e.g., 12",
    "counter": "one of the 'value' fields from the response above (e.g., 268:sandhikharka-khanepani)",
    "token": "Provided token"
}
</code></pre>

**Response:**
<pre><code class="json">
{
    "status": true,
    "customer_code": "1235",
    "customer_name": "पुर्ण कुमार",
    "address": "इटहरी-6, संगीत चौक",
    "mobile_number": "9841123456",
    "current_month_dues": "3000",
    "current_month_discount": "50",
    "current_month_fine": "0",
    "total_credit_sales_amount": "100",
    "total_advance_amount": "1000",
    "previous_dues": "0",
    "total_dues": "2950"
}
</code></pre>

**Description:**  
Fetch details for a specific Khanepani customer, including dues, discounts, and other relevant information.

### Khanepani Service Charge

**URL:** `{{base_url}}/api/servicegroup/servicecharge/khanepani/`  

**Note:**  
Khanepani service charge is Rs. 5 per transaction.

**Request Body:**
<pre><code class="json">
{
    "counter": "Counter Name",
    "token": "token",
    "amount": "Amount from detail fetch API"
}
</code></pre>

**Response:**
<pre><code class="json">
{
    "amount": 600,
    "service_charge": 5,
    "status": true
}
</code></pre>

**Description:**  
Calculate the service charge for the specified amount. The service charge applies to every transaction. 

### Khanepani Payment

**URL:** `{{base_url}}/api/servicegroup/commit/khanepani/`  
**Method:** ``POST``  

**Request Body:**
<pre><code class="json">
{
    "token":"token",
    "reference": "unique value sent for each request",
    "customer_code": "numeric value, e.g., 12",
    "counter": "one of the 'value' fields from the response above (e.g.268:sandhikharka-khanepani)",
    "amount": 5000
}
</code></pre>

**Note:**  
The amount in the payment API is without the service charge; the charge amount will be deducted from the service account.

**Response (Successful Payment):**
<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Success",
    "credits_consumed": 309,
    "credits_available": 35456464.966469494,
    "id": 78897534
}
</code></pre>

**Response (Due Amount):**
<pre><code class="json">
{
    "status": true,
    "detail": {
        "message": "Successful Payment",
        "due_amount": "1361"
    },
    "message": "Successfully Completed Transaction",
    "id": 181868,
    "extra_data": {},
    "state": "Success",
    "due_amount": "1361"
}
</code></pre>

**Description:**  
Process the payment for the specified amount and handle due amounts accordingly.