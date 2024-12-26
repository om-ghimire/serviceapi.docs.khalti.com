# KUKL Khanepani Counter Details

## API Endpoint

**URL**: `{{base_url}}/api/servicegroup/counters/kukl/`

**Method**: POST

## Request

The request should include the following **body**:

<pre><code class="json">
{
  "token": "{{token}}"
}
</code></pre>

## Response

A successful response will return the following JSON format:

<pre><code class="json">
{
    "status": true,
    "counters": [
        {
            "name": "Chettrapati",
            "value": "1114:test-kukl"
        }
    ]
}
</code></pre>

