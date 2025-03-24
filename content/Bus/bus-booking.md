# Bus Booking API Documentation

## Overview

This document describes the API for booking a bus ticket. The API allows users to specify their seat preferences and provides details about the booking confirmation.

## API Endpoint

**Request URL:** `{{url}}/api/servicegroup/book-v2/bus/`

**Request Method:** POST

### Request Parameters
<pre><code class="json">
{
    "token: "{{live_token}}",
    "session_id": "{{session_id}}",
    "bus_id": "{{bus_id}}",
    "seats": "[\"{{seat1}}\",\"{{seat2}}\"] (array of selected seats)"    
}
</code></pre>
## API Response

### Success Response

<pre><code class="json">
{
    "status": true,
    "detail": {
        "boarding_point": [
            "Gongabu Bus Park(06:00 AM)",
            "Basundhara(06:15 AM)",
            "Chabahil(06:30 AM)",
            "Gaushala(06:45 AM)",
            "Koteshwor(07:00 AM)",
            "Jadibutti(07:05 AM)",
            "Kasaultar(07:10 AM)",
            "Thimi(07:25 AM)",
            "Jagati(07:45 AM)",
            "Banepa(08:00 AM)",
            "Dhulikhel(08:15 AM)"
        ],
        "ticket_serial_no": "5115799-B"
    }
}
</code></pre>


## Conclusion

This API allows clients to book bus tickets by specifying their seat preferences. Ensure all provided parameters are valid for successful booking confirmation.
