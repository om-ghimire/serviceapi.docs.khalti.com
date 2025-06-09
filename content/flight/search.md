# Flight Search API

## Overview

The Flight Search API allows users to select flight details such as location, departure date, number of travelers, and nationality on the flight search page, returning available flight options for booking.


## API Details

- **URL:** `{{base_url}}/api/servicegroup/search/flight/`
- **Type:** Search API
- **Request Type:** GET

## Parameters

The request parameters should be provided in JSON format. Parameters vary based on the trip type: One Way (`O`) or Round Trip (`R`).

### For One Way (`O`)

<pre><code class="json">
{
    "flight_type": "<'D' for domestic or 'I' for international>",
    "trip_type": "'O'",
    "flight_date": "YYYY-MM-DD",
    "adult": "<Number of adults>",
    "child": "<Number of children>",
    "from": "<Origin sector code, e.g., 'PKR' for Pokhara>",
    "to": "<Destination sector code>",
    "token": "<provided_token>",
    "reference": "<unique_identifier>"
    "na
}
</code></pre>

### For Round Trip (`R`)

<pre><code class="json">
{
    "flight_type": "<'D' for domestic or 'I' for international>",
    "trip_type": "'R'",
    "flight_date": "YYYY-MM-DD",
    "return_date": "YYYY-MM-DD",
    "adult": "<Number of adults>",
    "child": "<Number of children>",
    "from": "<Origin sector code, e.g., 'PKR' for Pokhara>",
    "to": "<Destination sector code>",
    "token": "<provided_token>",
    "reference": "<unique_identifier>"
}
</code></pre>

### Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `flight_type` | Type of flight: `'D'` for domestic, `'I'` for international. |
| `trip_type` | Type of trip: `'O'` for one way, `'R'` for round trip. |
| `flight_date` | Departure date in `YYYY-MM-DD` format. |
| `return_date` | Return date in `YYYY-MM-DD` format (only for `trip_type: 'R'`). |
| `adult` | Number of adult passengers. |
| `child` | Number of child passengers. |
| `from` | Origin sector code (e.g., `'PKR'` for Pokhara, obtained from Flight Sector Listing API). |
| `to` | Destination sector code (obtained from Flight Sector Listing API). |
| `token` | Authentication token provided. |
| `reference` | Unique identifier for the request. |

## Success Response Format

The API returns flight options in JSON format, including details such as airline, flight number, fares, and baggage allowance. Responses vary based on trip type and whether flights include transit.

### One Way Without Transit

<pre><code class="json">
{
    "status": true,
    "booking_id": 17104,
    "outbound": [
        {
            "airline": "S1",
            "airline_name": "Saurya Airlines",
            "airline_logo": "https://dpuwrdlc4xu9f.cloudfront.net/services.khalti.com/static/images/airlines/S1.jpg",
            "flight_date": "2022-07-09",
            "flight_no": "S1171",
            "departure": "KATHMANDU",
            "departure_time": "06:00",
            "arrival": "BIRATNAGAR",
            "arrival_time": "06:27",
            "aircraft_type": "CRJ200",
            "adult": 1,
            "child": 0,
            "infant": 0,
            "flight_class_code": "S",
            "currency": "NPR",
            "adult_fare": 4000.0,
            "child_fare": 4000.0,
            "infant_fare": 0.0,
            "res_fare": 0.0,
            "fuel_surcharge": 0.0,
            "tax": 250.0,
            "refundable": false,
            "free_baggage": "20 + 5 KG KG",
            "fare_total": 4250.0,
            "commission": 0.0,
            "flight_id": "2c955b52-8744-4bd2-92c5-8b0c0fdb4df1:buddha",
            "agency_commission": 0.0,
            "child_commission": 0.0,
            "adult_commission": 0.0
        },
        {
            "airline": "S1",
            "airline_name": "Saurya Airlines",
            "airline_logo": "https://dpuwrdlc4xu9f.cloudfront.net/services.khalti.com/static/images/airlines/S1.jpg",
            "flight_date": "2022-07-09",
            "flight_no": "S1173",
            "departure": "KATHMANDU",
            "departure_time": "06:00",
            "arrival": "BIRATNAGAR",
            "arrival_time": "06:27",
            "aircraft_type": "CRJ200",
            "adult": 1,
            "child": 0,
            "infant": 0,
            "flight_class_code": "S",
            "currency": "NPR",
            "adult_fare": 4000.0,
            "child_fare": 4000.0,
            "infant_fare": 0.0,
            "res_fare": 0.0,
            "fuel_surcharge": 0.0,
            "tax": 250.0,
            "refundable": false,
            "free_baggage": "20 + 5 KG KG",
            "fare_total": 4250.0,
            "commission": 0.0,
            "flight_id": "e79c7218-0afc-4e5a-826c-ccab60c1b478:buddha",
            "agency_commission": 0.0,
            "child_commission": 0.0,
            "adult_commission": 0.0
        }
    ],
    "inbound": []
}
</code></pre>

### One Way With Transit

<pre><code class="json">
{
    "status": true,
    "booking_id": 86145,
    "outbound": [
        {
            "airline": "YT",
            "airline_name": "Yeti Airlines",
            "airline_logo": "https://dev-cdn.nayathegana.com/services.khalti.com/static/images/airlines/YT.jpg",
            "flight_date": "2025-01-16",
            "flight_no": "421",
            "departure": "KATHMANDU",
            "departure_time": "10:00",
            "arrival": "TIKAPUR",
            "arrival_time": "10:50",
            "aircraft_type": "ATR72",
            "adult": 1,
            "child": 0,
            "infant": 0,
            "flight_class_code": "E1",
            "currency": "NPR",
            "adult_fare": 7300,
            "child_fare": 0,
            "infant_fare": 0,
            "res_fare": 0,
            "fuel_surcharge": 1000,
            "tax": 200,
            "refundable": false,
            "free_baggage": "15.00 KG",
            "fare_total": 8500,
            "adult_commission": 0,
            "agency_commission": 0,
            "child_commission": 0,
            "infant_commission": 0,
            "commission": 0,
            "transit": [
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
            "flight_id": "F15F650F-5E1F-4B0E-BBF0-021F25D19279_E1C91938-6BB9-46C2-A5E9-FA66F5C4941B:yeti"
        }
    ],
    "inbound": []
}
</code></pre>

### Round Trip Without Transit

<pre><code class="json">
{
    "status": true,
    "booking_id": 17107,
    "outbound": [
        {
            "airline": "S1",
            "airline_name": "Saurya Airlines",
            "airline_logo": "https://dpuwrdlc4xu9f.cloudfront.net/services.khalti.com/static/images/airlines/S1.jpg",
            "flight_date": "2022-07-09",
            "flight_no": "S1171",
            "departure": "KATHMANDU",
            "departure_time": "06:00",
            "arrival": "BIRATNAGAR",
            "arrival_time": "06:27",
            "aircraft_type": "CRJ200",
            "adult": 1,
            "child": 0,
            "infant": 0,
            "flight_class_code": "S",
            "currency": "NPR",
            "adult_fare": 4000.0,
            "child_fare": 4000.0,
            "infant_fare": 0.0,
            "res_fare": 0.0,
            "fuel_surcharge": 0.0,
            "tax": 250.0,
            "refundable": false,
            "free_baggage": "20 + 5 KG KG",
            "fare_total": 4250.0,
            "commission": 0.0,
            "flight_id": "3b34cda3-7f71-433d-a211-3352178f37a4:buddha",
            "agency_commission": 0.0,
            "child_commission": 0.0,
            "adult_commission": 0.0
        },
        {
            "airline": "S1",
            "airline_name": "Saurya Airlines",
            "airline_logo": "https://dpuwrdlc4xu9f.cloudfront.net/services.khalti.com/static/images/airlines/S1.jpg",
            "flight_date": "2022-07-09",
            "flight_no": "S1173",
            "departure": "KATHMANDU",
            "departure_time": "06:00",
            "arrival": "BIRATNAGAR",
            "arrival_time": "06:27",
            "aircraft_type": "CRJ200",
            "adult": 1,
            "child": 0,
            "infant": 0,
            "flight_class_code": "S",
            "currency": "NPR",
            "adult_fare": 4000.0,
            "child_fare": 4000.0,
            "infant_fare": 0.0,
            "res_fare": 0.0,
            "fuel_surcharge": 0.0,
            "tax": 250.0,
            "refundable": false,
            "free_baggage": "20 + 5 KG KG",
            "fare_total": 4250.0,
            "commission": 0.0,
            "flight_id": "62e2b923-2e5a-44bd-91ce-a5e510d18c3f:buddha",
            "agency_commission": 0.0,
            "child_commission": 0.0,
            "adult_commission": 0.0
        }
    ],
    "inbound": [
        {
            "airline": "S1",
            "airline_name": "Saurya Airlines",
            "airline_logo": "https://dpuwrdlc4xu9f.cloudfront.net/services.khalti.com/static/images/airlines/S1.jpg",
            "flight_date": "2022-07-26",
            "flight_no": "S1174",
            "departure": "BIRATNAGAR",
            "departure_time": "07:00",
            "arrival": "KATHMANDU",
            "arrival_time": "07:27",
            "aircraft_type": "CRJ200",
            "adult": 1,
            "child": 0,
            "infant": 0,
            "flight_class_code": "S",
            "currency": "NPR",
            "adult_fare": 4000.0,
            "child_fare": 4000.0,
            "infant_fare": 0.0,
            "res_fare": 0.0,
            "fuel_surcharge": 0.0,
            "tax": 250.0,
            "refundable": false,
            "free_baggage": "15 + 5 KG KG",
            "fare_total": 4250.0,
            "commission": 0.0,
            "flight_id": "f7a71af2-23a9-4633-863a-4185fd91b6dc:buddha",
            "agency_commission": 0.0,
            "child_commission": 0.0,
            "adult_commission": 0.0
        },
        {
            "airline": "S1",
            "airline_name": "Saurya Airlines",
            "airline_logo": "https://dpuwrdlc4xu9f.cloudfront.net/services.khalti.com/static/images/airlines/S1.jpg",
            "flight_date": "2022-07-26",
            "flight_no": "S1172",
            "departure": "BIRATNAGAR",
            "departure_time": "07:00",
            "arrival": "KATHMANDU",
            "arrival_time": "07:27",
            "aircraft_type": "CRJ200",
            "adult": 1,
            "child": 0,
            "infant": 0,
            "flight_class_code": "S",
            "currency": "NPR",
            "adult_fare": 4000.0,
            "child_fare": 4000.0,
            "infant_fare": 0.0,
            "res_fare": 0.0,
            "fuel_surcharge": 0.0,
            "tax": 250.0,
            "refundable": false,
            "free_baggage": "15 + 5 KG KG",
            "fare_total": 4250.0,
            "commission": 0.0,
            "flight_id": "ca5d5e34-3ea1-4f73-a3f5-21b11a7e2fa8:buddha",
            "agency_commission": 0.0,
            "child_commission": 0.0,
            "adult_commission": 0.0
        },
        {
            "airline": "S1",
            "airline_name": "Saurya Airlines",
            "airline_logo": "https://dpuwrdlc4xu9f.cloudfront.net/services.khalti.com/static/images/airlines/S1.jpg",
            "flight_date": "2022-07-26",
            "flight_no": "S1172",
            "departure": "BIRATNAGAR",
            "departure_time": "07:00",
            "arrival": "KATHMANDU",
            "arrival_time": "07:27",
            "aircraft_type": "CRJ200",
            "adult": 1,
            "child": 0,
            "infant": 0,
            "flight_class_code": "R",
            "currency": "NPR",
            "adult_fare": 2840.0,
            "child_fare": 2840.0,
            "infant_fare": 0.0,
            "res_fare": 0.0,
            "fuel_surcharge": 1560.0,
            "tax": 250.0,
            "refundable": false,
            "free_baggage": "15 + 5 KG KG",
            "fare_total": 4650.0,
            "commission": 0.0,
            "flight_id": "31973aa9-40f8-4836-8e01-f9dda7c951eb:buddha",
            "agency_commission": 0.0,
            "child_commission": 0.0,
            "adult_commission": 0.0
        }
    ]
}
</code></pre>

### Round Trip With Transit

<pre><code class="json">
{
    "status": true,
    "booking_id": 86160,
    "outbound": [
        {
            "airline": "YT",
            "airline_name": "Yeti Airlines",
            "airline_logo": "https://dev-cdn.nayathegana.com/services.khalti.com/static/images/airlines/YT.jpg",
            "flight_date": "2025-01-19",
            "flight_no": "421",
            "departure": "KATHMANDU",
            "departure_time": "10:00",
            "arrival": "TIKAPUR",
            "arrival_time": "10:50",
            "aircraft_type": "ATR72",
            "adult": 2,
            "child": 0,
            "infant": 0,
            "flight_class_code": "E1",
            "currency": "NPR",
            "adult_fare": 7300,
            "child_fare": 0,
            "infant_fare": 0,
            "res_fare": 0,
            "fuel_surcharge": 1000,
            "tax": 200,
            "refundable": false,
            "free_baggage": "15.00 KG",
            "fare_total": 17000,
            "adult_commission": 0,
            "agency_commission": 0,
            "child_commission": 0,
            "infant_commission": 0,
            "commission": 0,
            "transit": [
                {
                    "airport": "KEP",
                    "flight_id": "99FB6E70-2F04-4705-8E22-F8ADD6236F16",
                    "departure_date": "2025-01-19",
                    "planned_departure_time": "12:30",
                    "planned_arrival_time": "12:45",
                    "name": "NEPALGUNJ",
                    "airline_code": "YT",
                    "flight_number": "421",
                    "status": "ACTIVE",
                    "flight_duration": "15"
                }
            ],
            "flight_id": "8C7FCAE1-160A-4C25-A56C-3390EF7FEB10_E1C91938-6BB9-46C2-A5E9-FA66F5C4941B:yeti"
        }
    ],
    "inbound": [
        {
            "airline": "YT",
            "airline_name": "Yeti Airlines",
            "airline_logo": "https://dev-cdn.nayathegana.com/services.khalti.com/static/images/airlines/YT.jpg",
            "flight_date": "2025-01-19",
            "flight_no": "1702",
            "departure": "TIKAPUR",
            "departure_time": "13:00",
            "arrival": "KATHMANDU",
            "arrival_time": "13:15",
            "aircraft_type": "DHT",
            "adult": 2,
            "child": 0,
            "infant": 0,
            "flight_class_code": "E1",
            "currency": "NPR",
            "adult_fare": 7300,
            "child_fare": 0,
            "infant_fare": 0,
            "res_fare": 0,
            "fuel_surcharge": 1000,
            "tax": 200,
            "refundable": false,
            "free_baggage": "15.00 KG",
            "fare_total": 17000,
            "adult_commission": 0,
            "agency_commission": 0,
            "child_commission": 0,
            "infant_commission": 0,
            "commission": 0,
            "transit": [
                {
                    "airport": "KEP",
                    "flight_id": "79362F7F-F056-4577-A3AC-C2E614F112A2",
                    "departure_date": "2025-01-19",
                    "planned_departure_time": "14:15",
                    "planned_arrival_time": "15:05",
                    "name": "NEPALGUNJ",
                    "airline_code": "YT",
                    "flight_number": "1702",
                    "status": "ACTIVE",
                    "flight_duration": "50"
                }
            ],
            "flight_id": "09A6B770-F7CD-4A65-B73E-C30FDEADE876_79AC2D88-6399-4AAB-9770-ABF1B780F2F4:yeti"
        }
    ]
}
</code></pre>

### Response Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `booking_id` | Booking ID for the transaction. Must be passed to the Flight Book API. |
| `airline` | Airline code (e.g., `SHA`, `U4`, `YT`). |
| `airline_name` | Name of the airline. |
| `airline_logo` | URL of the airline's logo. |
| `flight_date` | Date of the flight. |
| `flight_no` | Flight number. |
| `departure` | Departure location (from). |
| `departure_time` | Time of departure. |
| `arrival` | Arrival location (to). |
| `arrival_time` | Time of arrival. |
| `aircraft_type` | Type of aircraft. |
| `adult` | Number of adult passengers. |
| `child` | Number of child passengers. |
| `infant` | Number of infant passengers (obsolete, ignore this field). |
| `flight_class_code` | Type of flight class. |
| `currency` | Currency accepted by the airline (usually `NPR`). |
| `adult_fare` | Ticket price for adult passengers. |
| `child_fare` | Ticket price for child passengers. |
| `infant_fare` | Ticket price for infants (obsolete, ignore this field). |
| `res_fare` | Ticket price for residents (not currently used, reserved for future use). |
| `fuel_surcharge` | Total fuel surcharge. |
| `tax` | Total tax for the transaction. |
| `refundable` | Indicates if tickets are refundable (`true` or `false`). |
| `free_baggage` | Total free baggage allowance. |
| `fare_total` | Total ticket price. |
| `commission` | Total commission. |
| `flight_id` | Unique flight ID, used in the Flight Book API. |
| `agency_commission` | Agency commission (equals `adult_commission`). |
| `child_commission` | Total commission for child tickets. |
| `adult_commission` | Total commission for adult tickets. |

