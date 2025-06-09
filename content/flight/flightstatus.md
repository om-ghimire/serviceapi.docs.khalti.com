
# Flight Status API

The Flight Status API allows users to check the real-time status of flights for a specific airline and sector.

## API Details

- **URL:** `{{base_url}}/api/servicegroup/status/flight/`
- **Type:** Flight Status API
- **Request Type:** POST

## Parameters

The request body should be provided in JSON format.

<pre><code class="json">
{
    "token": "<provided_token>",
    "airline_id": "U4",
    "sector": "KTM-PKR"
}
</code></pre>

### Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `token` | Authentication token provided. |
| `airline_id` | Airline code obtained from the Flight Status Options API (e.g., `U4`). |
| `sector` | Flight sector in the format `<from>-<to>` (e.g., `KTM-PKR`). |

## Success Response Format

The API returns a JSON response with the status of flights for the specified airline and sector.

<pre><code class="json">
{
    "flight_status": [
        {
            "flight_no": "SHA-100",
            "departure": "KATHMANDU",
            "arrival": "POKHARA",
            "flight_time": "08:30",
            "revised_time": "08:40",
            "flight_status": "LANDED",
            "flight_remarks": "LANDED AT 08:59"
        },
        {
            "flight_no": "SHA-101",
            "departure": "KATHMANDU",
            "arrival": "POKHARA",
            "flight_time": "10:30",
            "revised_time": "10:30",
            "flight_status": "ONTIME",
            "flight_remarks": null
        },
        {
            "flight_no": "SHA-103",
            "departure": "KATHMANDU",
            "arrival": "POKHARA",
            "flight_time": "11:30",
            "revised_time": "12:30",
            "flight_status": "DELAY",
            "flight_remarks": "POKHARA AIRPORT CLOSED"
        }
    ],
    "status": true
}
</code></pre>

### Response Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `status` | Indicates if the request was successful (`true`). |
| `flight_status` | Array of flight status objects for the specified airline and sector. |
| `flight_no` | Flight number. |
| `departure` | Departure city. |
| `arrival` | Arrival city. |
| `flight_time` | Scheduled flight departure time. |
| `revised_time` | Revised departure time (if applicable). |
| `flight_status` | Current status of the flight (e.g., `LANDED`, `ONTIME`, `DELAY`). |
| `flight_remarks` | Additional remarks about the flight status (e.g., reason for delay or landing time). |

## Overview

The Flight Status API provides real-time status updates for flights operated by a specified airline on a given sector. It returns details such as flight number, departure and arrival cities, scheduled and revised times, and flight status (e.g., landed, on time, or delayed).

