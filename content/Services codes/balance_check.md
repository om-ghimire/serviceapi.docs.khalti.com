# Balance Check API Documentation

## Balance Check API

- **URL:** [https://uatservices.khalti.com/api/balance](https://uatservices.khalti.com/api/balance)
- **Method:** GET

### Request Parameters
<pre><code class="json">

{
  "token": "Provided Token"
}

</code></pre>

## Success Response

<pre><code class="json">

{
  "credits_consumed": 777099.369900001,
  "credits_available": 161155.5
}
</code></pre>

## Credits by Date API

**URL**: ``https://uatservices.khalti.com/api/credits/bydate/``

**Method**: ``POST``

**Request Parameters**

<pre><code class="json">

{
  "token": "<provided_token>",
  "date": "yy-mm-dd"
}
</code></pre>

## Success Response

<pre><code class="json">

{
  "credits_available": 454135.30317999,
  "status": true
}
</code></pre>

## Failure Response
<pre><code class="json">
{
  "detail": "Something Went Wrong",
  "status": false
}
</code></pre>


# Credit Request API

**URL**: ``https://uatservices.khalti.com/api/public/creditrequest/``

**Method**: ``POST``

**Request Parameters**
<pre><code class="json">
{
  "token": "provided_token",
  "credit": "Credit to be requested in float"
}
</code></pre>

## Success Response
**HTTP Status: 200 OK**

<pre><code class="json">
{
  "status": true,
  "detail": "Credit Requested"
}
</code></pre>
## Error Response

**HTTP Status: 400**

<pre><code class="json">
{
  "status": false,
  "detail": "Invalid Credit"
}
</code></pre>
## Mobile Operator Regular Expressions

<pre><code class="json">
{
  "^([98][50-9][0-9]{7})$": "nt-postpaid",
  "^([98][46][0-9]{7})$": "ntc",
  "^([97][4-5][0-9]{7})$": "nt-cdma",
  "^([98][0-2][0-9]{7})$": "ncell",
  "^([96][0-9]{8}|[98][8][0-9]{7})$": "smartcell"
}
</code></pre>