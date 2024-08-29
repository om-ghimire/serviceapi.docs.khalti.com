# Khalti Topup

## API Endpoint

- **URL**: [https://uatservices.khalti.com/api/use/khalti-topup/](https://uatservices.khalti.com/api/use/khalti-topup/)
- **Type**: Single Step API
- **METHOD**: POST

## Service Parameters

| Parameter | Description |
| --------- | ----------- |
| `token`   | The token provided for authentication. |
| `reference` | A unique reference for the transaction. |
| `amount`  | The amount to be recharged. |
| `number`  |  Khalti ID to which the top-up is to be done (e.g., 9841234567). |
| `remarks` | Optional field for any additional remarks. |

<pre><code class="json">
{
    "token": "token-provided",
    "reference": "unique-reference",
    "amount": "amount to be recharged",
    "number": "Unique Khalti ID to which TOPUP is to be done, eg: 9841234567",
    "remarks": "Remarks (Optional Field)"
}
</code></pre>

## Regex Patterns:  
<pre><code class="json">

[
    {
        "name": "NTC",
        "slug": "ntc",
        "pattern": "(9[8][46][0-9]{7})",
        "error_message": "Invalid mobile number"
    },
    {
        "name": "NCell",
        "slug": "ncell",
        "pattern": "(9[8][0-2][0-9]{7})",
        "error_message": "Invalid mobile number"
    },
    {
        "name": "Smartcell",
        "slug": "smartcell",
        "pattern": "(9[6][0-9]{8}|9[8][8][0-9]{7})",
        "error_message": "Invalid mobile number"
    },
    {
        "name": "NT CDMA",
        "slug": "nt-cdma",
        "pattern": "(9[7][4-5][0-9]{7})",
        "error_message": "Invalid mobile number"
    },
    {
        "name": "NT Postpaid",
        "slug": "nt-postpaid",
        "pattern": "(9[8][5][0-9]{7})",
        "error_message": "Invalid mobile number"
    }
]
</code></pre>



## Success Response 
<pre><code class="json">
{
    "id": 3116,
    "extra_data": {},
    "state": "Success",
    "detail": "Success",
    "message": "Successfully Completed Transaction",
    "status": true
}
</code></pre>



## Error Response  
<pre><code class="json">
{
    "status": false,
    "error_code": "4000",
    "message": "Can't fulfill request",
    "error": "client_error",
    "details": {
        "user": [
            "User does not exist."
        ],
        "http_status_code": 400
    },
    "error_data": {},
    "state": "Error"
}
</code></pre>