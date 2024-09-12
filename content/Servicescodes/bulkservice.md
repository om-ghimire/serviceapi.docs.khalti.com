# **BULK SERVICE STATUS LOOKUP API**

**URL:** `{{base_url}}/api/service/bulk/status/`  

**METHOD:** GET  

**Service Params:**
<pre><code class="json">
{
    "token": "<provided token>",
    "references": "JNK123,JNK124",  # Comma separated references
    "reference_length": 2  # Number of references sent
}
</code></pre>

**Response:**
<pre><code class="json">
{
    "status": true,
    "message": "Success",
    "detail": [
        {
            "status": true,
            "state": "Success",
            "details": "Payment made successfully. Account will be activated in few minutes",
            "reference": "cPCWiH2UPDjy8mjPyPXtPF",
            "response_id": 15845,
            "amount": 1400.0
        },
        {
            "status": true,
            "state": "Error",
            "details": "Invalid reference obtained for account",
            "reference": "JNK2",
            "response_id": 0,
            "amount": 0
        },
        {
            "status": true,
            "state": "Processing",
            "details": "",
            "reference": "8535",
            "response_id": 15686,
            "amount": 2000.0
        },
        {
            "status": true,
            "state": "Queued",
            "details": "",
            "reference": "f309e75f-3101-4139-bfa1-e7dff44e4276",
            "response_id": 15524,
            "amount": 3046.0
        }
    ]
}
</code></pre>

**NOTE:** Always check the `state` to make success/failure decisions. The list of possible states is listed Previous Page.
