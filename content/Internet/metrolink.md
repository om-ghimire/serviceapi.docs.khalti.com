# Metrolink Internet

**Type:** Single Step API

**Test URL:**  
`{{base_url}}/api/use/metrolink/`

**Method:**  
`POST`

**Service Parameters:**

<pre><code class="json">
{
    "token": "token",
    "username": "Username, eg: khaltiUser",
    "number": "9818766122",
    "amount": 100,  // Minimum Amount 100, Max: 50,000
    "address": "Banepa",
    "reference": "metrolink1"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "id": 1260,
    "credits_available": 9300.0,
    "message": "Your operation is in queue.",
    "state": "Queued",
    "credits_consumed": 100.0
}
</code></pre>
