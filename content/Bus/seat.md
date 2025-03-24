# Bus Seats Information API Documentation

## Overview

This document describes the API for retrieving seating information for a specific bus. The API provides details about the seat layout and their booking statuses.

## API Endpoint

**Request URL:** `{{base_url}}/api/servicegroup/seatsinfo/bus/`  
**Request Method:** POST

### Parameters
<pre><code class="json">
    "token":"{{token}}",
    "bus_id": "{{bus_id}}",
    "session_id": "{{session_id}}",
</code></pre>
## API Response

### Success Response

<pre><code class="json">
{
    "seat_layout": [
        {
            "display_name": "C1",
            "booking_status": "No"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "C2",
            "booking_status": "Yes"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "C3",
            "booking_status": "No"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "C4",
            "booking_status": "No"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "Bक",
            "booking_status": "No"
        },
        {
            "display_name": "Bख",
            "booking_status": "No"
        },
        {
            "display_name": "A1",
            "booking_status": "No"
        },
        {
            "display_name": "A2",
            "booking_status": "No"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "B1",
            "booking_status": "No"
        },
        {
            "display_name": "B2",
            "booking_status": "No"
        },
        {
            "display_name": "A3",
            "booking_status": "No"
        },
        {
            "display_name": "A4",
            "booking_status": "No"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "B3",
            "booking_status": "No"
        },
        {
            "display_name": "B4",
            "booking_status": "No"
        },
        {
            "display_name": "A5",
            "booking_status": "No"
        },
        {
            "display_name": "A6",
            "booking_status": "No"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "B5",
            "booking_status": "No"
        },
        {
            "display_name": "B6",
            "booking_status": "Yes"
        },
        {
            "display_name": "A7",
            "booking_status": "No"
        },
        {
            "display_name": "A8",
            "booking_status": "No"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "B7",
            "booking_status": "Yes"
        },
        {
            "display_name": "B8",
            "booking_status": "Yes"
        },
        {
            "display_name": "A9",
            "booking_status": "No"
        },
        {
            "display_name": "A10",
            "booking_status": "No"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "B9",
            "booking_status": "Yes"
        },
        {
            "display_name": "B10",
            "booking_status": "No"
        },
        {
            "display_name": "A11",
            "booking_status": "No"
        },
        {
            "display_name": "A12",
            "booking_status": "No"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "B11",
            "booking_status": "No"
        },
        {
            "display_name": "B12",
            "booking_status": "No"
        },
        {
            "display_name": "A13",
            "booking_status": "No"
        },
        {
            "display_name": "A14",
            "booking_status": "No"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "B13",
            "booking_status": "No"
        },
        {
            "display_name": "B14",
            "booking_status": "No"
        },
        {
            "display_name": "A15",
            "booking_status": "No"
        },
        {
            "display_name": "A16",
            "booking_status": "No"
        },
        {
            "display_name": "na",
            "booking_status": "na"
        },
        {
            "display_name": "B15",
            "booking_status": "No"
        },
        {
            "display_name": "B16",
            "booking_status": "No"
        },
        {
            "display_name": "A17",
            "booking_status": "No"
        },
        {
            "display_name": "A18",
            "booking_status": "No"
        },
        {
            "display_name": "19",
            "booking_status": "No"
        },
        {
            "display_name": "B17",
            "booking_status": "No"
        },
        {
            "display_name": "B18",
            "booking_status": "No"
        }
    ],
    "no_of_column": 5,
    "status": true
}
</code></pre>

## How to Construct Bus Seat Layout

These things must be considered while making the seat layout:

1. **Determine the Total Number of Columns**  
   For example, if `no_of_column` is 5, then the seat layout must have 5 columns.

   **Note:** The value for each seat must be checked from left to right as shown in the table below:

   | 1  | 2  | 3  | 4  | 5  |
   |----|----|----|----|----|
   | 6  | 7  | 8  | 9  | 10 |
   | 11 | 12 | 13 | 14 | 15 |

2. **Iterate for Each Cell**  
   - `displayName`: 
     - If "na", there is no seat.
     - If other than "na", that is the seat name or number.
   - `bookingStatus`: 
     - If "na", there is no seat.
     - If "Yes", the seat is booked.
     - If "No", the seat is available.

3. **Response for No Seat**

   <pre><code class="json">
   {
       "displayName": "na",
       "bookingStatus": "na"
   }
   </code></pre>

4. **Response for Booked Seat**

   <pre><code class="json">
   {
       "displayName": "A1",
       "bookingStatus": "Yes"
   }
   </code></pre>

5. **Response for Available Seat**

   <pre><code class="json">
   {
       "displayName": "A2",
       "bookingStatus": "No"
   }
   </code></pre>

### Example Seat Layout

This is how the seat layout might look based on the above responses:

|    |    |    |    |    |
|----|----|----|----|----|
| A1 | A2 |    | B1 | B2 |
| A3 | A4 |    | B3 | B4 |
| A5 | A6 |    | B5 | B6 |
| A7 | A8 |    | B7 | B8 |
| A9 | A10|    | B9 | B10|
| A11| A12|    | B11| B12|
| 14 | 15 |    | 16 | 17 |
| 18 |    |    |    |    |

## Conclusion

This API allows clients to retrieve seating information for a specified bus. Ensure the provided parameters are valid for successful responses.
