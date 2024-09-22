# NT FTTH

**Type:** Single Step API

## Payment API

- **Request URL:** `{{base_url}}/api/use/nt-ftth/`
- **Request Method:** POST

### Service Params

<pre><code class="json">
{
    "token": "\ token\ ",
    "number": "subscriber_number",   // e.g. 10000141001060
    "amount": 100,
    "reference": "\ Unique Identifier\ "
}
</code></pre>

### Notes

1. Amount should be between Rs. 10 and Rs. 25,000.
2. The `number` is the subscriber number of the user (14 characters).
3. The initial 5 characters are always constant: `10000`.

### Response Example

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Transaction successful",
    "credits_consumed": 100.0,
    "credits_available": 9997874087.88002,
    "id": 51510
}
</code></pre>

