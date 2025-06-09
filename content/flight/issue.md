# Flight Issue API

The Flight Issue API finalizes the issuance of flight tickets based on the booking details provided in earlier steps. This API requires a POST request and returns ticket details, including passenger information, PNR numbers, and fare details for one-way or round-trip flights, with or without transit.

## API Details

- **URL:** `{{base_url}}/api/servicegroup/issue/flight/`
- **Type:** Ticket Issuance API
- **Request Type:** POST

## Parameters

The request body should be provided in JSON format.

<pre><code class="json">
{
    "booking_id": "<value of booking_id from search response>",
    "token": "<provided_token>"
}
</code></pre>

### Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `booking_id` | Booking ID from the Flight Search API response. |
| `token` | Authentication token provided. |

## Success Response Format

The API returns ticket issuance details in JSON format, including flight details, passenger information, and transaction status. Responses vary based on trip type and whether flights include transit.

### One Way Without Transit

<pre><code class="json">
{
    "outbound": {
        "airline": "RMK",
        "airline_name": "RMK",
        "pnr_no": "SWOP7A",
        "flight_no": "RMK151",
        "arrival_time": "06:25:00",
        "departure_time": "06:00:00",
        "flight_class_code": "D",
        "currency": null,
        "fare_total": 3130,
        "reporting_time": "One Hour Before Flight Time"
    },
    "inbound": {
        "airline": "",
        "airline_name": "",
        "pnr_no": "",
        "flight_no": "",
        "arrival_time": "",
        "departure_time": "",
        "flight_class_code": "",
        "currency": null,
        "fare_total": 0,
        "inbound_reporting_time": ""
    },
    "flight_date": "2022-03-08",
    "return_date": "",
    "sector_from": "KTM",
    "sector_to": "PKR",
    "trip_type": "O",
    "passengers": [
        {
            "firstname": "TEST",
            "lastname": "TEST",
            "title": "MR",
            "passenger_type": "Adult",
            "gender": "Male",
            "ticket_no": "12345",
            "barcode": "",
            "inbound_ticket_no": "",
            "inbound_barcode": ""
        }
    ],
    "status": true,
    "log_ids": [
        32867
    ],
    "credits_available": 9999749517.42,
    "credits_consumed": 3130,
    "commission": 0,
    "state": "Success",
    "message": "Issue flight success"
}
</code></pre>

### One Way With Transit

<pre><code class="json">
{
    "outbound": {
        "airline": "YT",
        "airline_name": "YT",
        "pnr_no": "A5IXS5",
        "flight_no": "421",
        "arrival_time": "10:50:00",
        "departure_time": "10:00:00",
        "flight_class_code": "E1",
        "currency": null,
        "fare_total": 8500.0,
        "reporting_time": "One Hour Before Flight"
    },
    "inbound": {
        "airline": "YT",
        "airline_name": "Yeti Airlines",
        "pnr_no": "A5IXS5",
        "flight_no": "1702",
        "arrival_time": "13:15:00",
        "departure_time": "13:00:00",
        "flight_class_code": "E1",
        "currency": null,
        "fare_total": 8500.0,
        "inbound_reporting_time": "One Hour Before Flight"
    },
    "flight_date": "2025-01-28",
    "return_date": "2025-01-28",
    "sector_from": "KTM",
    "sector_to": "TPU",
    "trip_type": "R",
    "passengers": [
        {
            "firstname": "TEST",
            "lastname": "TEST",
            "title": "MR",
            "passenger_type": "Adult",
            "gender": "Male",
            "ticket_no": "9992109195070",
            "barcode": "",
            "inbound_ticket_no": "9992109195072",
            "inbound_barcode": "",
            "outbound_tickets": [
                {
                    "from": "KTM",
                    "to": "KEP",
                    "ticket_no": "9992109195070",
                    "flight_no": "421"
                },
                {
                    "from": "KEP",
                    "to": "TPU",
                    "ticket_no": "9992109195071",
                    "flight_no": "1701"
                }
            ],
            "inbound_tickets": [
                {
                    "from": "TPU",
                    "to": "KEP",
                    "ticket_no": "9992109195072",
                    "flight_no": "1702"
                },
                {
                    "from": "KEP",
                    "to": "KTM",
                    "ticket_no": "9992109195073",
                    "flight_no": "424"
                }
            ]
        }
    ],
    "status": true,
    "log_ids": [
        130334
    ],
    "credits_available": 998420049.14,
    "credits_consumed": 17000.0,
    "commission": 0.0,
    "state": "Success",
    "message": "Issue flight success"
}
</code></pre>

### Round Trip Without Transit

<pre><code class="json">
{
    "outbound": {
        "airline": "U4",
        "airline_name": "U4",
        "pnr_no": "PSW5RO",
        "flight_no": "U4601",
        "arrival_time": "07:15:00",
        "departure_time": "06:50:00",
        "flight_class_code": "Y",
        "currency": null,
        "fare_total": 11020,
        "reporting_time": "One Hour Before Flight Time"
    },
    "inbound": {
        "airline": "U4",
        "airline_name": "Buddha Airlines",
        "pnr_no": "QSW5RO",
        "flight_no": "U4602",
        "arrival_time": "07:15:00",
        "departure_time": "06:50:00",
        "flight_class_code": "Y",
        "currency": null,
        "fare_total": 11020,
        "inbound_reporting_time": "One Hour Before Flight Time"
    },
    "flight_date": "2022-04-19",
    "return_date": "2022-04-20",
    "sector_from": "KTM",
    "sector_to": "PKR",
    "trip_type": "R",
    "passengers": [
        {
            "firstname": "TEST",
            "lastname": "TEST",
            "title": "MR",
            "passenger_type": "Adult",
            "gender": "Male",
            "ticket_no": "12345",
            "barcode": "",
            "inbound_ticket_no": "13586310",
            "inbound_barcode": ""
        },
        {
            "firstname": "TEST",
            "lastname": "TEST",
            "title": "MR",
            "passenger_type": "Adult",
            "gender": "Male",
            "ticket_no": "12345",
            "barcode": "",
            "inbound_ticket_no": "",
            "inbound_barcode": ""
        }
    ],
    "status": true,
    "log_ids": [
        41714
    ],
    "credits_available": 9999495361.29,
    "credits_consumed": 22040,
    "commission": 0,
    "state": "Success",
    "message": "Issue flight success"
}
</code></pre>

### Round Trip With Transit

<pre><code class="json">
{
    "outbound": {
        "airline": "YT",
        "airline_name": "YT",
        "pnr_no": "A5IXS5",
        "flight_no": "421",
        "arrival_time": "10:50:00",
        "departure_time": "10:00:00",
        "flight_class_code": "E1",
        "currency": null,
        "fare_total": 8500.0,
        "reporting_time": "One Hour Before Flight"
    },
    "inbound": {
        "airline": "YT",
        "airline_name": "Yeti Airlines",
        "pnr_no": "A5IXS5",
        "flight_no": "1702",
        "arrival_time": "13:15:00",
        "departure_time": "13:00:00",
        "flight_class_code": "E1",
        "currency": null,
        "fare_total": 8500.0,
        "inbound_reporting_time": "One Hour Before Flight"
    },
    "flight_date": "2025-01-28",
    "return_date": "2025-01-28",
    "sector_from": "KTM",
    "sector_to": "TPU",
    "trip_type": "R",
    "passengers": [
        {
            "firstname": "TEST",
            "lastname": "TEST",
            "title": "MR",
            "passenger_type": "Adult",
            "gender": "Male",
            "ticket_no": "9992109195070",
            "barcode": "",
            "inbound_ticket_no": "9992109195072",
            "inbound_barcode": "",
            "outbound_tickets": [
                {
                    "from": "KTM",
                    "to": "KEP",
                    "ticket_no": "9992109195070",
                    "flight_no": "421"
                },
                {
                    "from": "KEP",
                    "to": "TPU",
                    "ticket_no": "9992109195071",
                    "flight_no": "1701"
                }
            ],
            "inbound_tickets": [
                {
                    "from": "TPU",
                    "to": "KEP",
                    "ticket_no": "9992109195072",
                    "flight_no": "1702"
                },
                {
                    "from": "KEP",
                    "to": "KTM",
                    "ticket_no": "9992109195073",
                    "flight_no": "424"
                }
            ]
        }
    ],
    "status": true,
    "log_ids": [
        130334
    ],
    "credits_available": 998420049.14,
    "credits_consumed": 17000.0,
    "commission": 0.0,
    "state": "Success",
    "message": "Issue flight success"
}
</code></pre>

### Response Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `airline` | Code of the airline (e.g., `RMK`, `YT`, `U4`). |
| `airline_name` | Name of the airline. |
| `pnr_no` | PNR number provided by the airline. |
| `flight_no` | Flight number provided by the airline. |
| `arrival_time` | Arrival time of the flight. |
| `departure_time` | Departure time of the flight. |
| `flight_class_code` | Code of the flight class. |
| `fare_total` | Total amount for the flight. |
| `reporting_time` | Time to be present at the airport, usually one hour before flight time. |
| `flight_date` | Date of departure. |
| `return_date` | Return date for round-trip flights. |
| `sector_from` | Departure city code (e.g., `KTM`). |
| `sector_to` | Arrival city code (e.g., `PKR`, `TPU`). |
| `trip_type` | Type of trip: `O` (One Way) or `R` (Round Trip). |
| `passengers` | Details of the passenger(s), including name, title, type, gender, and ticket numbers. |
| `status` | Indicates if the ticket issuance was successful (`true` or `false`). |
| `log_ids` | Log ID(s) for the flight booking. Single ID for one-way trips; single or multiple IDs for round trips, depending on the airline. |
| `credits_available` | Remaining credits after the transaction. |
| `credits_consumed` | Credits used for the transaction. |
| `commission` | Total commission for the booking. |
| `state` | State of the transaction: `Success` or `Error`. If not `Success` or `Error`, the Lookup API must be implemented. |
| `message` | Message describing the transaction outcome. |

## Overview

The Flight Issue API finalizes the issuance of flight tickets, providing detailed information about the flight, passengers, and transaction. It supports both one-way and round-trip tickets, with or without transit, and includes PNR numbers, ticket numbers, and fare details. The API requires the booking ID from the Flight Search API and a valid token to complete the ticket issuance process.# Flight Issue API

The Flight Issue API finalizes the issuance of flight tickets based on the booking details provided in earlier steps. This API requires a POST request and returns ticket details, including passenger information, PNR numbers, and fare details for one-way or round-trip flights, with or without transit.

## API Details

- **URL:** `{{base_url}}/api/servicegroup/issue/flight/`
- **Type:** Ticket Issuance API
- **Request Type:** POST

## Parameters

The request body should be provided in JSON format.

<pre><code class="json">
{
    "booking_id": "<value of booking_id from search response>",
    "token": "<provided_token>"
}
</code></pre>

### Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `booking_id` | Booking ID from the Flight Search API response. |
| `token` | Authentication token provided. |

## Success Response Format

The API returns ticket issuance details in JSON format, including flight details, passenger information, and transaction status. Responses vary based on trip type and whether flights include transit.

### One Way Without Transit

<pre><code class="json">
{
    "outbound": {
        "airline": "RMK",
        "airline_name": "RMK",
        "pnr_no": "SWOP7A",
        "flight_no": "RMK151",
        "arrival_time": "06:25:00",
        "departure_time": "06:00:00",
        "flight_class_code": "D",
        "currency": null,
        "fare_total": 3130,
        "reporting_time": "One Hour Before Flight Time"
    },
    "inbound": {
        "airline": "",
        "airline_name": "",
        "pnr_no": "",
        "flight_no": "",
        "arrival_time": "",
        "departure_time": "",
        "flight_class_code": "",
        "currency": null,
        "fare_total": 0,
        "inbound_reporting_time": ""
    },
    "flight_date": "2022-03-08",
    "return_date": "",
    "sector_from": "KTM",
    "sector_to": "PKR",
    "trip_type": "O",
    "passengers": [
        {
            "firstname": "TEST",
            "lastname": "TEST",
            "title": "MR",
            "passenger_type": "Adult",
            "gender": "Male",
            "ticket_no": "12345",
            "barcode": "",
            "inbound_ticket_no": "",
            "inbound_barcode": ""
        }
    ],
    "status": true,
    "log_ids": [
        32867
    ],
    "credits_available": 9999749517.42,
    "credits_consumed": 3130,
    "commission": 0,
    "state": "Success",
    "message": "Issue flight success"
}
</code></pre>

### One Way With Transit

<pre><code class="json">
{
    "outbound": {
        "airline": "YT",
        "airline_name": "YT",
        "pnr_no": "A5IXS5",
        "flight_no": "421",
        "arrival_time": "10:50:00",
        "departure_time": "10:00:00",
        "flight_class_code": "E1",
        "currency": null,
        "fare_total": 8500.0,
        "reporting_time": "One Hour Before Flight"
    },
    "inbound": {
        "airline": "YT",
        "airline_name": "Yeti Airlines",
        "pnr_no": "A5IXS5",
        "flight_no": "1702",
        "arrival_time": "13:15:00",
        "departure_time": "13:00:00",
        "flight_class_code": "E1",
        "currency": null,
        "fare_total": 8500.0,
        "inbound_reporting_time": "One Hour Before Flight"
    },
    "flight_date": "2025-01-28",
    "return_date": "2025-01-28",
    "sector_from": "KTM",
    "sector_to": "TPU",
    "trip_type": "R",
    "passengers": [
        {
            "firstname": "TEST",
            "lastname": "TEST",
            "title": "MR",
            "passenger_type": "Adult",
            "gender": "Male",
            "ticket_no": "9992109195070",
            "barcode": "",
            "inbound_ticket_no": "9992109195072",
            "inbound_barcode": "",
            "outbound_tickets": [
                {
                    "from": "KTM",
                    "to": "KEP",
                    "ticket_no": "9992109195070",
                    "flight_no": "421"
                },
                {
                    "from": "KEP",
                    "to": "TPU",
                    "ticket_no": "9992109195071",
                    "flight_no": "1701"
                }
            ],
            "inbound_tickets": [
                {
                    "from": "TPU",
                    "to": "KEP",
                    "ticket_no": "9992109195072",
                    "flight_no": "1702"
                },
                {
                    "from": "KEP",
                    "to": "KTM",
                    "ticket_no": "9992109195073",
                    "flight_no": "424"
                }
            ]
        }
    ],
    "status": true,
    "log_ids": [
        130334
    ],
    "credits_available": 998420049.14,
    "credits_consumed": 17000.0,
    "commission": 0.0,
    "state": "Success",
    "message": "Issue flight success"
}
</code></pre>

### Round Trip Without Transit

<pre><code class="json">
{
    "outbound": {
        "airline": "U4",
        "airline_name": "U4",
        "pnr_no": "PSW5RO",
        "flight_no": "U4601",
        "arrival_time": "07:15:00",
        "departure_time": "06:50:00",
        "flight_class_code": "Y",
        "currency": null,
        "fare_total": 11020,
        "reporting_time": "One Hour Before Flight Time"
    },
    "inbound": {
        "airline": "U4",
        "airline_name": "Buddha Airlines",
        "pnr_no": "QSW5RO",
        "flight_no": "U4602",
        "arrival_time": "07:15:00",
        "departure_time": "06:50:00",
        "flight_class_code": "Y",
        "currency": null,
        "fare_total": 11020,
        "inbound_reporting_time": "One Hour Before Flight Time"
    },
    "flight_date": "2022-04-19",
    "return_date": "2022-04-20",
    "sector_from": "KTM",
    "sector_to": "PKR",
    "trip_type": "R",
    "passengers": [
        {
            "firstname": "TEST",
            "lastname": "TEST",
            "title": "MR",
            "passenger_type": "Adult",
            "gender": "Male",
            "ticket_no": "12345",
            "barcode": "",
            "inbound_ticket_no": "13586310",
            "inbound_barcode": ""
        },
        {
            "firstname": "TEST",
            "lastname": "TEST",
            "title": "MR",
            "passenger_type": "Adult",
            "gender": "Male",
            "ticket_no": "12345",
            "barcode": "",
            "inbound_ticket_no": "",
            "inbound_barcode": ""
        }
    ],
    "status": true,
    "log_ids": [
        41714
    ],
    "credits_available": 9999495361.29,
    "credits_consumed": 22040,
    "commission": 0,
    "state": "Success",
    "message": "Issue flight success"
}
</code></pre>

### Round Trip With Transit

<pre><code class="json">
{
    "outbound": {
        "airline": "YT",
        "airline_name": "YT",
        "pnr_no": "A5IXS5",
        "flight_no": "421",
        "arrival_time": "10:50:00",
        "departure_time": "10:00:00",
        "flight_class_code": "E1",
        "currency": null,
        "fare_total": 8500.0,
        "reporting_time": "One Hour Before Flight"
    },
    "inbound": {
        "airline": "YT",
        "airline_name": "Yeti Airlines",
        "pnr_no": "A5IXS5",
        "flight_no": "1702",
        "arrival_time": "13:15:00",
        "departure_time": "13:00:00",
        "flight_class_code": "E1",
        "currency": null,
        "fare_total": 8500.0,
        "inbound_reporting_time": "One Hour Before Flight"
    },
    "flight_date": "2025-01-28",
    "return_date": "2025-01-28",
    "sector_from": "KTM",
    "sector_to": "TPU",
    "trip_type": "R",
    "passengers": [
        {
            "firstname": "TEST",
            "lastname": "TEST",
            "title": "MR",
            "passenger_type": "Adult",
            "gender": "Male",
            "ticket_no": "9992109195070",
            "barcode": "",
            "inbound_ticket_no": "9992109195072",
            "inbound_barcode": "",
            "outbound_tickets": [
                {
                    "from": "KTM",
                    "to": "KEP",
                    "ticket_no": "9992109195070",
                    "flight_no": "421"
                },
                {
                    "from": "KEP",
                    "to": "TPU",
                    "ticket_no": "9992109195071",
                    "flight_no": "1701"
                }
            ],
            "inbound_tickets": [
                {
                    "from": "TPU",
                    "to": "KEP",
                    "ticket_no": "9992109195072",
                    "flight_no": "1702"
                },
                {
                    "from": "KEP",
                    "to": "KTM",
                    "ticket_no": "9992109195073",
                    "flight_no": "424"
                }
            ]
        }
    ],
    "status": true,
    "log_ids": [
        130334
    ],
    "credits_available": 998420049.14,
    "credits_consumed": 17000.0,
    "commission": 0.0,
    "state": "Success",
    "message": "Issue flight success"
}
</code></pre>

### Response Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `airline` | Code of the airline (e.g., `RMK`, `YT`, `U4`). |
| `airline_name` | Name of the airline. |
| `pnr_no` | PNR number provided by the airline. |
| `flight_no` | Flight number provided by the airline. |
| `arrival_time` | Arrival time of the flight. |
| `departure_time` | Departure time of the flight. |
| `flight_class_code` | Code of the flight class. |
| `fare_total` | Total amount for the flight. |
| `reporting_time` | Time to be present at the airport, usually one hour before flight time. |
| `flight_date` | Date of departure. |
| `return_date` | Return date for round-trip flights. |
| `sector_from` | Departure city code (e.g., `KTM`). |
| `sector_to` | Arrival city code (e.g., `PKR`, `TPU`). |
| `trip_type` | Type of trip: `O` (One Way) or `R` (Round Trip). |
| `passengers` | Details of the passenger(s), including name, title, type, gender, and ticket numbers. |
| `status` | Indicates if the ticket issuance was successful (`true` or `false`). |
| `log_ids` | Log ID(s) for the flight booking. Single ID for one-way trips; single or multiple IDs for round trips, depending on the airline. |
| `credits_available` | Remaining credits after the transaction. |
| `credits_consumed` | Credits used for the transaction. |
| `commission` | Total commission for the booking. |
| `state` | State of the transaction: `Success` or `Error`. If not `Success` or `Error`, the Lookup API must be implemented. |
| `message` | Message describing the transaction outcome. |

