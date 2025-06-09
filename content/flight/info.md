# Flight Status Options API

The Flight Status Options API provides a list of available airline codes and names for use in the Flight Status API.

## API Details

- **URL:** `{{base_url}}/api/servicegroup/info/flight/`
- **Type:** Flight Status Options API
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

The API returns a JSON response with a list of airline codes and their corresponding names.

<pre><code class="json">
{
    "status": true,
    "options": [
        {
            "airline": "Buddha Air",
            "code": "U4"
        },
        {
            "airline": "Saurya Airlines",
            "code": "S1"
        },
        {
            "airline": "Guna Airlines",
            "code": "GUA"
        },
        {
            "airline": "Shree Airlines",
            "code": "SHA"
        },
        {
            "airline": "Sita Air",
            "code": "ST"
        }
    ]
}
</code></pre>

### Response Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `status` | Indicates if the request was successful (`true`). |
| `options` | Array of airline objects containing airline names and codes. |
| `airline` | Name of the airline (e.g., `Buddha Air`). |
| `code` | Airline code (e.g., `U4`). |

## Overview

The Flight Status Options API provides a list of airline codes and names that can be used in the Flight Status API to check flight statuses. This API is essential for identifying valid airline IDs for status queries.
