# Ncell Data Pack API Documentation

### Overview

The Ncell Data Pack API provides two main functionalities:

1. **Get Packages API**: Retrieve available Ncell data pack options.

2. **Ncell Data Pack Payment API**: Process payment for a selected Ncell data pack.

### Get Packages API

**Request URL:**  
`https://uatservices.khalti.com/api/servicegroup/getpackages/ncell-product/`

**Request Method:** POST

**Service Parameters:**

<pre><code class="json">
{
    "token": "<token>"
}

</code></pre>


<pre><code class="json">
{
    "status": true,
    "detail": {
        "packages": [
            {
                "priority_no": 1,
                "product_name": "100 Minute Call Time 1",
                "amount": 50.55,
                "short_detail": "100 Minute Call Time 1",
                "product_code": "PROD_001_inv",
                "description": "100 Minute Call Time 1",
                "prodcut_type": "All Packs",
                "validity": "1 Day",
                "package_priority": 100
            },
            {
                "priority_no": 1,
                "product_name": "Seasonal Call offer 1",
                "amount": 199.99,
                "short_detail": "seasonal call offer",
                "product_code": "Test_Pr_001",
                "description": "Seasonal Call offer 1",
                "prodcut_type": "All Packs",
                "validity": "7 Days",
                "package_priority": 0
            },
            {
                "priority_no": 90,
                "product_name": "Ncell Product",
                "amount": 55.0,
                "short_detail": "109",
                "product_code": "1_day_10min_India",
                "description": "At just Rs.55, get 15 minutes India talktime valid for 1 day.",
                "prodcut_type": "Voice Pack",
                "validity": "10 Days",
                "package_priority": 1
            },
            {
                "priority_no": 90,
                "product_name": "1 Day Voice Pack",
                "amount": 10.0,
                "short_detail": "1 Day Voice Pack",
                "product_code": "S173284",
                "description": "1 Day Voice Pack",
                "prodcut_type": "Voice Pack",
                "validity": "28 Days",
                "package_priority": 0
            }
        ]
    }
}
</code></pre>

## Ncell Data Pack Payment API

### Request URL:
  ```https://uatservices.khalti.com/api/use/ncell-product/```

***Request Method***: POST

### Service Parameters:
<pre><code class="json">
{
    "token": "<token>",
    "amount": 98.99,
    "number": "9809399558",
    "reference": "reference123",
    "product_code": "Per_Day_300MB"
}
</code></pre>

### Success Response:

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Transaction successful",
    "id": 7276
}
</code></pre>

### Error Response

<pre><code class="json">
{
    "status": false,
    "error_code": "001",
    "message": "The parameters sent are not correct.",
    "error": "invalid_parameters",
    "details": {
        "product_code": "Invalid Product Code"
    },
    "error_data": {
        "product_code": "Invalid Product Code"
    },
    "state": "Error"
}

</code></pre>