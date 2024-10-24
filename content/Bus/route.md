# Bus Routes API Documentation

## Overview

This document describes the API for fetching bus routes. The API provides a list of available bus routes and their corresponding labels.

## API Endpoint

**Request URL:** `{{base_url}}/api/servicegroup/routes/bus/`  
**Request Method:** POST

### Parameters
<pre><code class="json">
{
 "token": "{{token}}"
}
</code></pre>

## API Response

### Success Response

<pre><code class="json">
{
    "status": true,
    "routes": [
        {
            "label": "radhe radhe",
            "value": "radhe radhe"
        },
        {
            "label": "Bardibas chock",
            "value": "Bardibas chock"
        },
        {
            "label": "Kathmandu Valley",
            "value": "Kathmandu Valley"
        },
        {
            "label": "Lumbini",
            "value": "Lumbini"
        },
        {
            "label": "Kakadvitta",
            "value": "Kakadvitta"
        },
        {
            "label": "Sindhuli",
            "value": "Sindhuli"
        },
        {
            "label": "Gaur",
            "value": "Gaur"
        },
        {
            "label": "Nepalgunj",
            "value": "Nepalgunj"
        },
        {
            "label": "Damauli",
            "value": "Damauli"
        },
        {
            "label": "Hile",
            "value": "Hile"
        },
        {
            "label": "Khurkot",
            "value": "Khurkot"
        },
        {
            "label": "Budhabare",
            "value": "Budhabare"
        },
        {
            "label": "Kakarbhitta",
            "value": "Kakarbhitta"
        },
        {
            "label": "Surunga",
            "value": "Surunga"
        },
        {
            "label": "Biratnagar",
            "value": "Biratnagar"
        },
        {
            "label": "Gaushala",
            "value": "Gaushala"
        },
        {
            "label": "Besisahar",
            "value": "Besisahar"
        },
        {
            "label": "CG Shashwat Dham",
            "value": "CG Shashwat Dham"
        },
        {
            "label": "Dhangadhi",
            "value": "Dhangadhi"
        },
        {
            "label": "Jaleshwor",
            "value": "Jaleshwor"
        }
    ]
}
</code></pre>

## Conclusion

This API allows clients to retrieve a list of bus routes. Ensure the token is valid for successful responses.
