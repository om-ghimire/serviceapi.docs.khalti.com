# Flight Add Info API

The Flight Add Info API allows users to submit passenger details for a flight booking, including contact information and details for each passenger. This API requires a POST request and must include passenger details matching the number of adults and children specified in the Flight Search API.

## API Details

- **URL:** `{{base_url}}/api/servicegroup/addinfo/flight/`
- **Type:** Passenger Details API
- **Request Type:** POST

## Parameters

The request body should be provided in JSON format, including contact information and a list of passengers.

<pre><code class="json">
{
    "token": "<provided_token>",
    "contact_name": "<name of contact person>",
    "booking_id": "<value of booking_id from search response>",
    "contact_phone": "<phone of contact person>",
    "passengers": [
        {
            "firstname": "<First Name of passenger>",
            "lastname": "<Last Name of passenger>",
            "type": "<ADULT, CHILD>",
            "title": "<MR, MRS or MS>",
            "gender": "<M or F>",
            "nationality": "<Country code of the passenger (NP for Nepal, IN for Indian)>"
        },
        ...
    ]
}
</code></pre>

**Note:** The `passengers` list must include details for each passenger, matching the number of adults and children specified in the Flight Search API. For example, if the search specified 1 adult and 1 child, the list must contain two entries: one with `type: 'ADULT'` and one with `type: 'CHILD'`.

### Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `token` | Authentication token provided. |
| `contact_name` | Name of the contact person. |
| `contact_phone` | Contact phone number of the contact person. |
| `booking_id` | Booking ID from the Flight Search API response. |
| `firstname` | First name of the passenger. |
| `lastname` | Last name of the passenger. |
| `type` | Type of passenger: `ADULT` or `CHILD`. |
| `title` | Title of the passenger: `MR`, `MRS`, or `MS`. |
| `gender` | Gender of the passenger: `M` (Male) or `F` (Female). |
| `nationality` | Nationality of the passenger: `NP` (Nepali) or `IN` (Indian). |

## Success Response Format

The API returns a simple JSON response indicating the success of the passenger details submission.

<pre><code class="json">
{
    "status": true
}
</code></pre>

## Error Responses

### 1. Mismatch in Number of Adult/Child Passengers

If the number of adult or child passengers in the `passengers` list does not match the counts specified in the Flight Search API (e.g., specifying a child when an adult was expected).

<pre><code class="json">
{
    "status": false,
    "error_code": "1011",
    "message": "Validation error",
    "error": "validation_error",
    "details": {
        "childrens": "Number of childrens passengers mismatched",
        "adults": "Number of adults passengers mismatched"
    },
    "error_data": {
        "childrens": "Number of childrens passengers mismatched",
        "adults": "Number of adults passengers mismatched"
    },
    "state": "Error"
}
</code></pre>

### 2. Empty or Missing Fields

If required fields (e.g., `gender`) are empty or missing in the `passengers` list.

<pre><code class="json">
{
    "status": false,
    "error_code": "1011",
    "message": "Validation error",
    "error": "validation_error",
    "details": {
        "passengers": [
            {
                "gender": "This field cannot be blank"
            }
        ]
    },
    "error_data": {
        "passengers": [
            {
                "gender": "This field cannot be blank"
            }
        ]
    },
    "state": "Error"
}
</code></pre>

