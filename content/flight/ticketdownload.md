# Flight Ticket Download API

The Flight Ticket Download API allows users to download flight tickets in PDF format or as base64-encoded data, using the log IDs obtained from the Flight Issue API. This API requires a GET request and is typically used to retrieve tickets from the "My Bookings" page.

## API Details

- **URL:** `{{base_url}}/api/download/<id>`
- **Type:** Ticket Download API
- **Request Type:** GET
- **`<id>`:** Log ID from the `log_ids` field in the Flight Issue API response.

## Parameters

The request body should be provided in JSON format. The `is_base64` parameter is optional.

<pre><code class="json">
{
    "token": "<provided_token>",
    "is_base64": <boolean>
}
</code></pre>

**Note:**
- In case of multiple log IDs received in the Flight Issue API, each log ID corresponds to a separate downloadable flight ticket.
- If you need the PDF attachment, ignore the `is_base64` parameter (no need to send it).
- If `is_base64` is set to `true`, the response returns base64-encoded data; otherwise, it returns a PDF attachment.

### Parameter Descriptions

| Parameter | Description |
|-----------|-------------|
| `token` | Authentication token provided. |
| `is_base64` | Optional boolean field. If `true`, returns base64-encoded data; if omitted or `false`, returns a PDF attachment. |

## Success Response Format

The API returns either a PDF file attachment or base64-encoded data, depending on the `is_base64` parameter. Specific response formats (e.g., JSON structure or file details) are not provided, as the output is either a binary PDF or an encoded string.

