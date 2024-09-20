# Nijgad Cable API

## 1. FOR CABLE TV

### Fetch TV Package API

- **Request URL**: `{{base_url}}/api/servicegroup/getpackages/nijgadh-cable/`
- **Request Method**: POST  

#### Service Parameters

To fetch available TV packages, send the following JSON object:

<pre><code class="json">
{
    "token": "token",
    "type": "tv"
}
</code></pre>

#### Response Format

The response will be in the following format:

<pre><code class="json">
{
    "status": true,
    "detail": {
        "packages": [
            {
                "package_name": "Basic TV Package - 1Month",
                "amount": 325
            },
            {
                "package_name": "Basic TV Package - 3Month",
                "amount": 975
            },
            {
                "package_name": "Basic TV Package - 6Month",
                "amount": 1550
            },
            {
                "package_name": "Basic TV Package - 1Year",
                "amount": 3000
            },
            {
                "package_name": "HD TV Package - 1Month",
                "amount": 525
            },
            {
                "package_name": "HD TV Package - 3Month",
                "amount": 1075
            },
            {
                "package_name": "HD TV Package - 6Month",
                "amount": 2575
            },
            {
                "package_name": "HD TV Package - 1Year",
                "amount": 5075
            }
        ]
    }
}
</code></pre>

### TV Payment API

- **Request URL**: `{{base_url}}/api/use/nijgadh-cable/`
- **Request Method**: POST  

#### Service Parameters

To make a payment for the selected TV package, send the following JSON object:

<pre><code class="json">
{
    "token": "token",
    "reference": "reference123",
    "username": "khaltiUser",
    "full_name": "Khalti User",
    "mobile_number": "9841xxxxxx",
    "package": "HD Plus Child TV Package - 1Year",  // from detail API
    "amount": 8000,
    "tv_identifier": "132465"  // Should be cas_id(6 digit), box_number(10 digits), or smart_card_number(12)
}
</code></pre>

#### Response Format

Upon a successful transaction, the API will return the following response:

<pre><code class="json">
{
    "status": true,
    "state": "Queued",
    "detail": "Transaction Queued",
    "message": "Your operation is in queue.",
    "credits_consumed": 8000.0,
    "credits_available": 96688310.0450002,
    "extra_data": {},
    "id": 7515
}
</code></pre>

## 2. FOR INTERNET

### Fetch Internet Package API

- **Request URL**: `{{base_url}}/api/servicegroup/getpackages/nijgadh-cable/`
- **Request Method**: POST  

#### Service Parameters

To fetch available internet packages, send the following JSON object:

<pre><code class="json">
{
    "token": "token",
    "type": "internet"
}
</code></pre>

#### Response Format

The response will be in the following format:

<pre><code class="json">
{
    "status": true,
    "detail": {
        "packages": [
            {
                "package_name": "Internet Package - 1Month 20Mbps",
                "amount": 1150
            },
            {
                "package_name": "Internet Package - 3Month 20Mbps",
                "amount": 3150
            },
            {
                "package_name": "Internet Package - 6Month 20Mbps",
                "amount": 7015
            },
            {
                "package_name": "Internet Package - 12Month 20Mbps",
                "amount": 12600
            },
            {
                "package_name": "Internet Package - 1Month 30Mbps",
                "amount": 1375
            },
            {
                "package_name": "Internet Package - 3Month 30Mbps",
                "amount": 3945
            },
            {
                "package_name": "Internet Package - 6Month 30Mbps",
                "amount": 7530
            },
            {
                "package_name": "Internet Package - 12Month 30Mbps",
                "amount": 13635
            },
            {
                "package_name": "Internet Package - 1Month 40Mbps",
                "amount": 1615
            },
            {
                "package_name": "Internet Package - 3Month 40Mbps",
                "amount": 4655
            },
            {
                "package_name": "Internet Package - 6Month 40Mbps",
                "amount": 8955
            },
            {
                "package_name": "Internet Package - 12Month 40Mbps",
                "amount": 16480
            },
            {
                "package_name": "Internet Package - 1Month 75Mbps",
                "amount": 2446
            },
            {
                "package_name": "Internet Package - 3Month 75Mbps",
                "amount": 7150
            },
            {
                "package_name": "Internet Package - 6Month 75Mbps",
                "amount": 13615
            },
            {
                "package_name": "Internet Package - 12Month 75Mbps",
                "amount": 26450
            }
        ]
    }
}
</code></pre>

### Internet Payment API

- **Request URL**: `{{base_url}}/api/use/nijgadh-cable/`
- **Request Method**: POST  

#### Service Parameters

To make a payment for the selected internet package, send the following JSON object:

<pre><code class="json">
{
    "token": "token",
    "reference": "reference123",
    "user_id": "khaltiUser",
    "name": "Khalti User",
    "mobile_number": "9841xxxxxx",
    "package": "Internet Package - 12Month 75Mbps",  // from detail API
    "amount": 26450
}
</code></pre>

#### Response Format

Upon a successful transaction, the API will return the following response:

<pre><code class="json">
{
    "status": true,
    "state": "Queued",
    "detail": "Transaction Queued",
    "message": "Your operation is in queue.",
    "credits_consumed": 26450.0,
    "credits_available": 96688310.0450002,
    "extra_data": {},
    "id": 7515
}
</code></pre>
