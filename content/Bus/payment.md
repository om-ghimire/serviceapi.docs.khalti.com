# Commit Bus Booking API Documentation

## Overview

This document describes the API for committing a bus booking transaction. The API finalizes the booking process and returns transaction details.

## API Endpoint

**Request URL:** `{{base_url}}/api/servicegroup/commit-v2/bus/`  
**Request Method:** POST

### Request Parameters

- **token**: `{{token}}`
- **session_id**: `{{session_id}}`

### API Response

#### Success Response

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": {
        "bus_no": "",
        "message": "Booking Successfully Done",
        "ticket_serial_number": "810610-101576400",
        "contact_info": [
            "Counter: ",
            "Contact Number: "
        ]
    }
}
</code></pre>



## Conclusion

This API allows clients to finalize their bus booking transaction and provides essential details regarding the booking. Ensure all provided parameters are valid for successful completion.
