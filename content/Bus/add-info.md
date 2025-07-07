# Add Info for  API Documentation

## Overview

This document describes the API for adding passenger information after booking a bus ticket. The API allows users to provide details such as boarding points and passenger information before proceeding to payment.

## API Endpoint

**Request URL:** `{{base_url}}/api/servicegroup/addinfo-v2/bus/`  
**Request Method:** POST

### Request Body

<pre><code class="json">
{
    "token": "{{token}}",
    "session_id": "{{session_id}}",
    "bus_id": "{{bus_id}}",
    "ticket_serial_no": "{{ticket_serial_no}}",  // Optional: Do not send if not obtained in Book Bus API
    "mobile_number": "9843223423",
    "boarding_point": "{{boarding_point}}",
    "email": "test@okay.com",
    "name": "TEST",
    "seats": "[{\"seat\":\"{{seat1}}\",\"fullName0\":\"test trest A\",\"nationality\":\"nepali\",\"age0\":\"25\"},{\"seat\":\"{{seat2}}\",\"fullName1\":\"test trest A\",\"nationality\":\"nepali\",\"age1\":\"25\"}]"
}
</code></pre>

### API Response

#### Success Response

<pre><code class="json">
{
    "status": true,
    "detail": "Now you can proceed to the payment.",
    "ticket_serial_no": ""
}
</code></pre>


## Conclusion

This API allows clients to add passenger information necessary for completing the bus booking process. Ensure all provided parameters are valid for successful processing before proceeding to payment.
