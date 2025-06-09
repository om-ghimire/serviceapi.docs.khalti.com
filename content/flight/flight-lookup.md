# Flight Status Lookup API

The Flight Status Lookup API allows users to check the status of flight bookings, including ticket issuance and cancellation details, using the reference ID from the issue or payment step. This API requires a GET request and returns detailed flight information, including outbound and inbound flight status, passenger details, and any cancellation information.

## API Details

- **URL:** `{{base_url}}/api/flight/status`
- **Type:** Status Lookup API
- **Request Type:** GET

## Parameters

The request body should be provided in JSON format.

<pre><code class="json">
{
    "token": "<provided token>",
    "reference": "<reference used during issue/payment step>"
}
</code></pre>

### Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `token` | Authentication token provided. |
| `reference` | Reference ID used during the flight issue or payment step. |

## Success Response Format

The API returns a JSON response with detailed flight status information, including flight details, passenger information, and cancellation status (if applicable). Responses vary based on trip type and whether flights include transit.

### One Way Flight Without Transit

<pre><code class="json">
{
    "status": true,
    "detail": {
        "outbound_state": "Issued",
        "outbound_status": "Success",
        "flight_id": "fb696c57-d132-4fcd-ab55-f6af16456d0d:buddha",
        "reference": "66088aae-a082-4d27-ab43-4d68c6748448",
        "response_id": 48139,
        "outbound": {
            "airline": "U4",
            "airline_name": "U4",
            "pnr_no": "YOO5SO",
            "flight_no": "U4651",
            "arrival_time": "07:30:00",
            "departure_time": "07:05:00",
            "flight_class_code": "Y",
            "currency": null,
            "fare_total": 5510.0,
            "reporting_time": "One Hour Before Flight Time"
        },
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
        ]
    }
}
</code></pre>

### One Way Flight With Transit

<pre><code class="json">
{
    "status": true,
    "detail": {
        "outbound_state": "Issued",
        "outbound_status": "Success",
        "flight_id": "ad8cd5ab-1c70-42be-8293-3f6bb32ae56e_e1c91938-6bb9-46c2-a5e9-fa66f5c4941b:yeti",
        "reference": "d6f7eed1-e55d-4ec7-ab23-79ef41772cbe",
        "response_id": 130338,
        "outbound": {
            "airline": "YT",
            "airline_name": "YT",
            "pnr_no": "A5IXS6",
            "flight_no": "421",
            "arrival_time": "10:50:00",
            "departure_time": "10:00:00",
            "flight_class_code": "E1",
            "currency": null,
            "fare_total": 8500.0,
            "reporting_time": "One Hour Before Flight"
        },
        "passengers": [
            {
                "firstname": "TEST",
                "lastname": "TEST",
                "title": "MR",
                "passenger_type": "Adult",
                "gender": "Male",
                "ticket_no": "9992109195074",
                "barcode": "",
                "inbound_ticket_no": "",
                "inbound_barcode": "",
                "outbound_tickets": [
                    {
                        "to": "KEP",
                        "from": "KTM",
                        "flight_no": "421",
                        "ticket_no": "9992109195074"
                    },
                    {
                        "to": "TPU",
                        "from": "KEP",
                        "flight_no": "1701",
                        "ticket_no": "9992109195075"
                    }
                ],
                "inbound_tickets": []
            }
        ]
    }
}
</code></pre>

### Two Way Flight Without Transit

<pre><code class="json">
{
    "status": true,
    "detail": {
        "outbound_state": "Issued",
        "outbound_status": "Success",
        "flight_id": "5b255f58-be72-4119-a7f7-f7615febd41c:buddha",
        "reference": "ef738e04-e3cd-4ec5-bbc9-7313fd1bc4cc",
        "response_id": 48320,
        "outbound": {
            "airline": "U4",
            "airline_name": "U4",
            "pnr_no": "JPO5SO",
            "flight_no": "U4651",
            "arrival_time": "07:30:00",
            "departure_time": "07:05:00",
            "flight_class_code": "Y",
            "currency": null,
            "fare_total": 11020.0,
            "reporting_time": "One Hour Before Flight Time"
        },
        "inbound_state": "Issued",
        "inbound_status": "Success",
        "inbound_flight_id": "569ae0ea-7e18-4237-b562-cd879c0e7ff2:buddha",
        "inbound": {
            "airline": "GUA",
            "airline_name": "Guna Airlines",
            "pnr_no": "JLMX8A",
            "flight_no": "GUA1662",
            "arrival_time": "09:23:00",
            "departure_time": "09:00:00",
            "flight_class_code": "Y",
            "currency": null,
            "fare_total": 11020.0,
            "inbound_reporting_time": "One Hour Before Flight Time"
        },
        "passengers": [
            {
                "firstname": "TEST",
                "lastname": "TEST",
                "title": "MR",
                "passenger_type": "Adult",
                "gender": "Male",
                "ticket_no": "12345",
                "barcode": "",
                "inbound_ticket_no": "122341",
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
        ]
    }
}
</code></pre>

### Two Way Flight With Transit

<pre><code class="json">
{
    "status": true,
    "detail": {
        "outbound_state": "Issued",
        "outbound_status": "Success",
        "flight_id": "ad8cd5ab-1c70-42be-8293-3f6bb32ae56e_e1c91938-6bb9-46c2-a5e9-fa66f5c4941b:yeti",
        "reference": "ac9aaa8c-a62b-4fb9-9f30-b32ec0e04dca",
        "response_id": 130334,
        "outbound": {
            "airline": "YT",
            "airline_name": "YT",
            "pnr_no": "A5IXS5",
            "flight_no": "421",
            "arrival_time": "10:50:00",
            "departure_time": "10:00:00",
            "flight_class_code": "E1",
            "currency": null,
            "fare_total": 8500,
            "reporting_time": "One Hour Before Flight"
        },
        "inbound_state": "Issued",
        "inbound_status": "Success",
        "inbound_flight_id": "ec0e3dda-dd5a-4c82-9b91-b5d40333a852_79ac2d88-6399-4aab-9770-abf1b780f2f4:yeti",
        "inbound": {
            "airline": "YT",
            "airline_name": "Yeti Airlines",
            "pnr_no": "A5IXS5",
            "flight_no": "1702",
            "arrival_time": "13:15:00",
            "departure_time": "13:00:00",
            "flight_class_code": "E1",
            "currency": null,
            "fare_total": 8500,
            "inbound_reporting_time": "One Hour Before Flight"
        },
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
                        "to": "KEP",
                        "from": "KTM",
                        "flight_no": "421",
                        "ticket_no": "9992109195070"
                    },
                    {
                        "to": "TPU",
                        "from": "KEP",
                        "flight_no": "1701",
                        "ticket_no": "9992109195071"
                    }
                ],
                "inbound_tickets": [
                    {
                        "to": "KEP",
                        "from": "TPU",
                        "flight_no": "1702",
                        "ticket_no": "9992109195072"
                    },
                    {
                        "to": "KTM",
                        "from": "KEP",
                        "flight_no": "424",
                        "ticket_no": "9992109195073"
                    }
                ]
            }
        ]
    }
}
</code></pre>

### Two Way Flight With Cancelled Tickets

For a round-trip booking with two adult passengers where one inbound and one outbound ticket have been cancelled:

<pre><code class="json">
{
    "status": true,
    "detail": {
        "outbound_state": "Issued",
        "outbound_status": "Partial Success",
        "flight_id": "b66e5721-61ef-4ff3-a718-959ba32d857f:buddha",
        "reference": "a58f2a4b-92a5-4232-a078-b6b8737f3f97",
        "response_id": 48332,
        "outbound": {
            "airline": "U4",
            "airline_name": "U4",
            "pnr_no": "OPO5SO",
            "flight_no": "U4651",
            "arrival_time": "07:30:00",
            "departure_time": "07:05:00",
            "flight_class_code": "Y",
            "currency": null,
            "fare_total": 11020,
            "reporting_time": "One Hour Before Flight Time"
        },
        "inbound_state": "Issued",
        "inbound_status": "Partial Success",
        "inbound_flight_id": "61ef2cfa-30ae-49d8-ae02-f2432641eaaf:buddha",
        "inbound": {
            "airline": "GUA",
            "airline_name": "Guna Airlines",
            "pnr_no": "KLMX8A",
            "flight_no": "GUA1662",
            "arrival_time": "09:23:00",
            "departure_time": "09:00:00",
            "flight_class_code": "Y",
            "currency": null,
            "fare_total": 11020,
            "inbound_reporting_time": "One Hour Before Flight Time"
        },
        "passengers": [
            {
                "firstname": "SHRESTHA",
                "lastname": "TEST",
                "title": "MR",
                "passenger_type": "Adult",
                "gender": "Male",
                "ticket_no": "12345",
                "barcode": "",
                "inbound_ticket_no": "122343",
                "inbound_barcode": ""
            },
            {
                "firstname": "TEST",
                "lastname": "SHRESTHA",
                "title": "MR",
                "passenger_type": "Adult",
                "gender": "Male",
                "ticket_no": "12345",
                "barcode": "",
                "inbound_ticket_no": "122344",
                "inbound_barcode": ""
            }
        ],
        "cancel_tickets": [
            {
                "cancel": true,
                "status": "Success",
                "reference": "a58f2a4b-92a5-4232-a078-b6b8737f3f97",
                "response_id": 48332,
                "ticket_type": "inbound",
                "extra_charge": 200,
                "flight_charge": 0,
                "ticket_number": "122343"
            },
            {
                "cancel": true,
                "status": "Success",
                "reference": "a58f2a4b-92a5-4232-a078-b6b8737f3f97",
                "response_id": 48332,
                "ticket_type": "outbound",
                "extra_charge": 100,
                "flight_charge": 0,
                "ticket_number": "13589065"
            }
        ]
    }
}
</code></pre>

### Response Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `status` | Overall status of the request (`true` indicates the request was processed successfully). |
| `detail` | Object containing detailed flight status information. |
| `outbound_state` | State of the outbound flight (e.g., `Issued`). |
| `outbound_status` | Status of the outbound flight (e.g., `Success`, `Partial Success`). |
| `flight_id` | Unique ID of the outbound flight. |
| `reference` | Reference ID used during the issue or payment step. |
| `response_id` | Unique ID for the response. |
| `outbound` | Object containing outbound flight details (airline, PNR, flight number, times, etc.). |
| `inbound_state` | State of the inbound flight (e.g., `Issued`, for round trips). |
| `inbound_status` | Status of the inbound flight (e.g., `Success`, `Partial Success`, for round trips). |
| `inbound_flight_id` | Unique ID of the inbound flight (for round trips). |
| `inbound` | Object containing inbound flight details (airline, PNR, flight number, times, etc., for round trips). |
| `passengers` | Array of passenger details, including name, title, type, gender, and ticket numbers. |
| `cancel_tickets` | Array of cancelled ticket details (if applicable), including ticket type, number, and charges. |
| `cancel_tickets.cancel` | Indicates if the ticket was cancelled (`true` or `false`). |
| `cancel_tickets.status` | Status of the cancellation (e.g., `Success`). |
| `cancel_tickets.reference` | Reference ID for the cancellation. |
| `cancel_tickets.response_id` | Response ID for the cancellation. |
| `cancel_tickets.ticket_type` | Type of ticket cancelled (e.g., `outbound`, `inbound`). |
| `cancel_tickets.extra_charge` | Additional charges for cancellation (e.g., fees). |
| `cancel_tickets.flight_charge` | Flight charges related to cancellation (if any). |
| `cancel_tickets.ticket_number` | Number of the cancelled ticket. |

