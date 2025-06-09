# Flight Sector Listing API

The Flight Sector Listing API allows users to retrieve a list of available flight sectors, including their names, codes, and status for domestic or international flights. This API requires a POST request and returns sector details to be used in other flight-related APIs, such as the Flight Search API.

## API Details

- **URL:** `{{base_url}}/api/servicegroup/sectors/flight/`
- **Type:** Sector Listing API
- **Request Type:** POST

## Parameters

The request body should be provided in JSON format.

<pre><code class="json">
{
    "token": "<provided_token>"
}
</code></pre>

### Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `token` | Authentication token provided. |

## Success Response Format

The API returns a list of flight sectors in JSON format, including details such as sector name, code, and whether the sector is active for national or international flights.

<pre><code class="json">
{
    "status": true,
    "sectors": [
        {
            "name": "Bhadrapur",
            "code": "BDP",
            "is_national": true,
            "is_international": false,
            "is_active": true
        },
        {
            "name": "Bhairahawa",
            "code": "BWA",
            "is_national": true,
            "is_international": false,
            "is_active": false
        },
        {
            "name": "Bharatpur",
            "code": "BHR",
            "is_national": true,
            "is_international": false,
            "is_active": false
        }
    ]
}
</code></pre>

### Response Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `status` | Indicates if the request was successful (`true` or `false`). |
| `sectors` | Array of sector objects containing details about each flight sector. |
| `name` | Name of the sector (e.g., city or airport name). |
| `code` | Unique sector code (e.g., `BDP` for Bhadrapur). |
| `is_national` | Indicates if the sector is available for domestic flights (`true` or `false`). |
| `is_international` | Indicates if the sector is available for international flights (`true` or `false`). |
| `is_active` | Indicates if the sector is currently active (`true` or `false`). |

