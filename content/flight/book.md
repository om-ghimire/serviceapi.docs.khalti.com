# Flight Book API
## Overview

The Flight Book API enables users to confirm flight bookings using flight and booking IDs from the Flight Search API. It supports both one-way and round-trip bookings, with or without transit, and provides commission details and a ticket purchase time limit. Error responses are returned for cases such as already booked flights or invalid flight ID selections.

## API Details

- **URL:** `{{base_url}}/api/servicegroup/book/flight/`
- **Type:** Booking API
- **Request Type:** POST

## Parameters

The request body should be provided in JSON format. Parameters vary based on the trip type: One Way or Round Trip.

### For One Way

<pre><code class="json">
{
    "flight_id": "<one of the flight_ids from search response outbound list>",
    "booking_id": "<value of booking_id from search response>",
    "token": "<provided_token>"
}
</code></pre>

### For Round Trip

<pre><code class="json">
{
    "flight_id": "<one of the flight_ids from search response outbound list>",
    "return_flight_id": "<OPTIONAL: flight id from inbound list>",
    "booking_id": "<value of booking_id from search response>",
    "token": "<provided_token>"
}
</code></pre>

### Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `flight_id` | The ID of the specific flight to book, obtained from the Flight Search API's outbound list. |
| `return_flight_id` | Flight ID from the inbound list of the Flight Search API, used if `trip_type` is `'R'` (Round Trip). Optional. |
| `booking_id` | Booking ID from the Flight Search API response. |
| `token` | Authentication token provided. |

## Success Response Format

The API returns booking confirmation details in JSON format, including flight IDs, commission details, and the ticket purchase time limit (TTL). Responses vary based on trip type and whether flights include transit.

### One Way Without Transit

<pre><code class="json">
{
    "status": true,
    "ttl": "2022-07-05T06:17:00Z",
    "flight_id": "5592deba-a390-44a0-97e6-a9fb2a036bba:buddha",
    "inbound_flight_id": "",
    "commission": 0.0,
    "adult_commission": 0.0,
    "child_commission": 0.0,
    "inbound_commission": 0.0,
    "inbound_adult_commission": 0.0,
    "inbound_child_commission": 0.0
}
</code></pre>

### One Way With Transit

<pre><code class="json">
{
    "status": true,
    "ttl": "2025-01-13T10:28:45.360300Z",
    "flight_id": "f15f650f-5e1f-4b0e-bbf0-021f25d19279_e1c91938-6bb9-46c2-a5e9-fa66f5c4941b:yeti",
    "inbound_flight_id": "",
    "include_vat": false,
    "outbound_transit": [
        {
            "airport": "KEP",
            "flight_id": "A4E73BF9-D0BB-44E5-9C3D-11589B99C433",
            "departure_date": "2025-01-16",
            "planned_departure_time": "12:30",
            "planned_arrival_time": "12:45",
            "name": "NEPALGUNJ",
            "airline_code": "YT",
            "flight_number": "421",
            "status": "ACTIVE",
            "flight_duration": "15"
        }
    ],
    "inbound_transit": [],
    "commission": 0,
    "adult_commission": 0,
    "child_commission": 0,
    "inbound_commission": 0,
    "inbound_adult_commission": 0,
    "inbound_child_commission": 0
}
</code></pre>

### Round Trip Without Transit

<pre><code class="json">
{
    "status": true,
    "ttl": "2022-07-05T06:25:00Z",
    "flight_id": "ed3632f1-b406-44a2-a0a2-6af7f0b6d31d:buddha",
    "inbound_flight_id": "102b2a75-6dcf-44a6-8a39-b9cec0487fc1:buddha",
    "commission": 196.0,
    "adult_commission": 98.0,
    "child_commission": 98.0,
    "inbound_commission": 196.0,
    "inbound_adult_commission": 0.0,
    "inbound_child_commission": 0.0
}
</code></pre>

### Round Trip With Transit

<pre><code class="json">
{
    "status": true,
    "ttl": "2025-01-16T11:39:17.679522Z",
    "flight_id": "ad8cd5ab-1c70-42be-8293-3f6bb32ae56e_e1c91938-6bb9-46c2-a5e9-fa66f5c4941b:yeti",
    "inbound_flight_id": "ec0e3dda-dd5a-4c82-9b91-b5d40333a852_79ac2d88-6399-4aab-9770-abf1b780f2f4:yeti",
    "include_vat": false,
    "outbound_transit": [
        {
            "airport": "KEP",
            "flight_id": "92B86639-BEB6-4620-8188-DD369747733A",
            "departure_date": "2025-01-28",
            "planned_departure_time": "12:30",
            "planned_arrival_time": "12:45",
            "name": "NEPALGUNJ",
            "airline_code": "YT",
            "flight_number": "421",
            "status": "ACTIVE",
            "flight_duration": "15"
        }
    ],
    "inbound_transit": [
        {
            "airport": "KEP",
            "flight_id": "A2244348-D472-4EC6-A7AD-4AB20F9A0CFB",
            "departure_date": "2025-01-28",
            "planned_departure_time": "14:15",
            "planned_arrival_time": "15:05",
            "name": "NEPALGUNJ",
            "airline_code": "YT",
            "flight_number": "1702",
            "status": "ACTIVE",
            "flight_duration": "50"
        }
    ],
    "commission": 0,
    "adult_commission": 0,
    "child_commission": 0,
    "inbound_commission": 0,
    "inbound_adult_commission": 0,
    "inbound_child_commission": 0
}
</code></pre>

### Response Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `status` | Status of the flight booking (`true` or `false`). |
| `ttl` | Ticket purchase time limit (in ISO 8601 format). |
| `flight_id` | The ID of the booked outbound flight. |
| `inbound_flight_id` | The ID of the booked inbound flight (for round trips only). |
| `commission` | Total commission for the outbound flight. |
| `adult_commission` | Commission for a single adult ticket for the outbound flight. |
| `child_commission` | Commission for a single child ticket for the outbound flight. |
| `inbound_commission` | Total commission for the inbound flight (for round trips). |
| `inbound_adult_commission` | Commission for a single adult ticket for the inbound flight. |
| `inbound_child_commission` | Commission for a single child ticket for the inbound flight. |

**Note:** Commissions must be respected as returned by the Flight Book API.

## Error Responses

### 1. Flight Already Booked

<pre><code class="json">
{
    "status": false,
    "error_code": "7000",
    "message": "Unknown Error occurred. Check details",
    "error": "unknown_error",
    "details": "Already booked",
    "error_data": {},
    "state": "Error"
}
</code></pre>

### 2. Same Flight ID and Return Flight ID

<pre><code class="json">
{
    "status": false,
    "error_code": "7000",
    "message": "Unknown Error occurred. Check details",
    "error": "unknown_error",
    "details": "inappropriate flight id",
    "error_data": {},
    "state": "Error"
}
</code></pre>

