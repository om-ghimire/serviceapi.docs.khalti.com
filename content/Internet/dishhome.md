
# Dish Home API

Dishhome is a TV/ISP payment service that allows users to pay for various services, including regular recharges, Dishhome FTTH (ISP), Dishhome combos, and special offers. This API consists of two main endpoints for fetching service details and processing payments.

## Type: Multi Step API

### 1. Detail Fetch API

This endpoint retrieves detailed information about the user's Dish Home package.

#### Request

- **Request URL:** `{{base_url}}/api/servicegroup/details/dishhome-updated/`
- **Request Method:** `POST`
- **Service Params:**

<pre><code class="json">
{
    "token": "token",
    "customer_id": "customer_id",
    "reference": "unique reference"
}
</code></pre>

#### Response

The response includes various details about the customer's package, including available recharge options.

<pre><code class="json">
{
    "response_code": 200,
    "package": "Basic Package",
    "quantity": 1,
    "expiry_date": "2037-11-28T11:15:00",
    "zone": "Mid-West | Bheri Zone",
    "district": "Surkhet",
    "customer_type": "House",
    "customer_status": "Prepaid On",
    "customer_id": 1111,
    "customer_class": "1-Residential",
    "isp_customer_id": "",
    "yearly_price": 4800.0,
    "packages": [
        {
            "description": "1 Month",
            "price": 400.0,
            "duration_type": 1,
            "bonus": 0.0,
            "is_regular": false,
            "idx": 1
        },
        {
            "description": "3 Months",
            "price": 1200.0,
            "duration_type": 3,
            "bonus": 400.0,
            "is_regular": false,
            "idx": 2
        },
        {
            "description": "6 Months",
            "price": 2399.0,
            "duration_type": 6,
            "bonus": 1201.0,
            "is_regular": false,
            "idx": 3
        },
        {
            "description": "12 Months",
            "price": 4800.0,
            "duration_type": 12,
            "bonus": 4800.0,
            "is_regular": false,
            "idx": 4
        },
        {
            "description": "Regular",
            "price": 2000.0,
            "duration_type": 0,
            "bonus": 400.0,
            "is_regular": true,
            "idx": 5
        },
        {
            "description": "Regular",
            "price": 1000.0,
            "duration_type": 0,
            "bonus": 100.0,
            "is_regular": true,
            "idx": 6
        },
        {
            "description": "Regular",
            "price": 700.0,
            "duration_type": 0,
            "bonus": 35.0,
            "is_regular": true,
            "idx": 7
        },
        {
            "description": "Regular",
            "price": 600.0,
            "duration_type": 0,
            "bonus": 30.0,
            "is_regular": true,
            "idx": 8
        },
        {
            "description": "Regular",
            "price": 500.0,
            "duration_type": 0,
            "bonus": 25.0,
            "is_regular": true,
            "idx": 9
        }
    ],
    "session_id": 20520,
    "status": true
}
</code></pre>

### 2. Payment API

This endpoint processes the payment for the selected Dish Home package.

#### Request

- **Request URL:** `{{base_url}}/api/servicegroup/commit/dishhome-updated/`
- **Request Method:** `POST`
- **Service Params:**

<pre><code class="json">
{
    "token": "token",
    "session_id": "\ session_id\ ",
    "package_id": "\ idx\ "
}
</code></pre>

#### Response

The response provides details about the transaction status, including updated balance and transaction ID.

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": {
        "response_code": 200,
        "response_description": "Successfully Recharged",
        "updated_balance": -1591.5836,
        "expiry_date": "2024-06-14T11:15:00",
        "customer_status": "Active",
        "transaction_id": 140251146,
        "recharged_amount": 500,
        "is_bonus_added": true
    },
    "credits_consumed": 500,
    "credits_available": 19987322608.1098,
    "id": 109657
}
</code></pre>
