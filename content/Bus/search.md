# Bus Search API Documentation

## Overview

This document describes the API for searching buses between specified locations. The API allows users to find available buses based on their travel preferences.

## API Endpoint

**Request URL:** `{{url}}/api/servicegroup/search-v2/bus/`  
**Request Method:** GET

### Parameters
<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "from": "from",
    "to": "to",
    "date": "date"
}
</code></pre>

## API Response

### Success Response

<pre><code class="json">
{
    "status": true,
    "buses": [
        {
            "id": "gongabu-buspark:12746",
            "ticket_price": 2170,
            "departure_time": "05:30 AM",
            "is_tourist_bus": false,
            "bus_type": "NBus 43(C4 B2 L1)",
            "amenities": [],
            "date_en": "2024-09-26",
            "operator": "Chandika Yatayat",
            "bus_no": "C31P1D-HILE",
            "commission": 0
        }
    ],
    "session_id": 15005
}
</code></pre>

### Error Response

<pre><code class="json">
{
    "status": false,
    "error_code": "4000",
    "message": "Can't fulfill request",
    "error": "client_error",
    "details": "Buses for this day could not be found",
    "error_data": {},
    "state": "Error"
}
</code></pre>

## Conclusion

This API allows clients to search for buses between specified locations. Ensure the provided parameters are correct for successful responses.
