# Flight Cancel API

The Flight Cancel API allows users to request the cancellation of flight tickets by specifying the booking ID and ticket numbers. This API requires a POST request and returns the status of the cancellation request for each ticket.

!!! Note 
    Your cancel request will be pending until we cancel it from here. Once we manually cancel it from our end, the DLR callback or status lookup API must be implemented. In DLR callback API, the API must be provided from your end, and we will be sending you response about the status.

## API Details

- **URL:** `{{base_url}}/api/servicegroup/cancel/flight/`
- **Type:** Cancellation API
- **Request Type:** POST

## Parameters

The request body should be provided in JSON format, with the `cancel_tickets` parameter formatted as a JSON array of strings.

<pre><code class="json">
{
    "booking_id": "<booking_id from search step>",
    "cancel_tickets": ["222915", "222111"],
    "token": "<provided_token>"
}
</code></pre>

**Note:** The `cancel_tickets` parameter must be an array of strings, with each string representing a ticket number. The format should be `["ticket_number_1", "ticket_number_2"]`, and the request accepts multipart form-data.

### Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `booking_id` | Booking ID obtained from the Flight Search API. |
| `cancel_tickets` | Array of ticket numbers to be canceled, formatted as a JSON array of strings (e.g., `["222915", "222111"]`). |
| `token` | Authentication token provided. |

## Success Response Format

The API returns a JSON response indicating the status of the cancellation request for each ticket.

<pre><code class="json">
{
    "status": true,
    "cancel_request_tickets": [
        {
            "status": true,
            "ticket_type": "outbound",
            "ticket_number": "123456"
        }
    ]
}
</code></pre>

## Error Response Format

The API returns a JSON response indicating a failure in the cancellation request for one or more tickets.

<pre><code class="json">
{
    "status": true,
    "cancel_request_tickets": [
        {
            "status": false,
            "ticket_type": "",
            "ticket_number": 123456
        }
    ]
}
</code></pre>

### Response Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `status` | Overall status of the cancellation request (`true` indicates the request was processed, even if individual tickets failed). |
| `cancel_request_tickets` | Array of objects detailing the cancellation status for each ticket. |
| `cancel_request_tickets.status` | Status of the individual ticket cancellation (`true` for success, `false` for failure). |
| `cancel_request_tickets.ticket_type` | Type of ticket (e.g., `outbound` or empty if not applicable). |
| `cancel_request_tickets.ticket_number` | Ticket number submitted for cancellation. |


!!! Note
    Total amount to be charged for cancellation = flight\_charge \+ extra\_charge