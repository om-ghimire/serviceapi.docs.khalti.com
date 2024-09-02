# **Sagarmatha Lumbini Insurance API**

## Detail Fetch API

**Request URL**: {{base_url}}/api/servicegroup/details/sagarmatha-insurance/

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
  "token": "Provided Token",
  "debit_note_no": "Debit Note no of client> (TEST DEBIT NOTE NO : 001618/198500779)",
  "reference": "unique identifier"
}
</code></pre>

**Response**:

<pre><code class="json">
{
  "contact_no": "9861233462",
  "debit_note_no": "001618/198500778",
  "session_id": 171,
  "address": "Tathali - 3, Bhaktapur, Bagmati",
  "name": "Bal Sundar Raut",
  "status": true,
  "payable_amount": "1010"
}
</code></pre>

## Payment API

**Request URL**: {{base_url}}/api/servicegroup/commit/sagarmatha-insurance/

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
  "token": "Account_Token",
  "session_id": "session_id returned during user lookup",
  "amount": "premium amount to be paid from details step"
}
</code></pre>

**Response**:

<pre><code class="json">
{
  "bill_info": {
    "tax_invoice_no": "18740",
    "receipt_no": "24211",
    "document_no": "111618/198500702"
  },
  "id": 3523,
  "extra_data": {},
  "state": "Success",
  "detail": "Successful Payment",
  "message": "Successfully Completed Transaction",
  "status": true
}
</code></pre>
