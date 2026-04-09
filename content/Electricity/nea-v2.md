# NEA (Nepal Electricity Authority) API – Updated Documentation

---

## 1. Get Counters API

**URL:**
```
{{base_url}}/api/servicegroup/counters/nea-v2/
```

**Description:**
Retrieves the list of all available counters.

 **Request Body**:
<pre><code class="json">
{
    "token": "{{token}}"
}
</code></pre>

**Response Fields:**
- **name**: Name of the counter  
- **migrated_to_v2**: Indicates whether NEA V1 or NEA V2 should be used  
- **value**: Value to be passed in subsequent APIs  
- **org_no**: Organization number  

**Success Response:**
<pre><code class="json">
{
    "counters": [
        {
            "name": "BALAJU",
            "value": "245:balaju-dc",
            "org_no": "110311901",
            "migrated_to_v2": true
        }
    ],
    "status": true
}
</code></pre>

**Logic:**
- If `migrated_to_v2 = false` → Use **NEA V1 APIs**  
- If `migrated_to_v2 = true` → Use **NEA V2 APIs**

---

## 2. NEA V2 Detail Fetch API

**URL:**
```
{{base_url}}/api/servicegroup/details/nea-v2/
```

**Method:** POST

  **Description:**
Fetches billing details using the updated consumer number.

  **Request Body:**
<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "request_no": "1001595737",
    "confirm_type": "Energy Charge",
    "confirm_id_type": "Consumer Number"
}
</code></pre>

  **Parameters:**
- **request_no**: New consumer number (provided by NEA)  
- **confirm_type**: Always `Energy Charge` *(may support additional values in future)*  
- **confirm_id_type**: Always `Consumer Number` *(may support additional values in future)*  

---

  **Sample Response – Due Bill:**
<pre><code class="json">
{
    "session_id": 19259,
    "consumer_name": "DIPESH KHATRI",
    "total_due_amount": "1874.83",
    "due_bills": [
        {
            "feeType": "Power Charge",
            "feeSubType": "Power Charge",
            "rcvblID": "676683371",
            "feeAmount": "988.00",
            "payableAmount": "1232.75",
            "billDate": "20251220",
            "billMonth": "208209",
            "days": "47",
            "rebate": "0.00",
            "penalty": "246.55",
            "status": "+25% Penalty",
            "rcvedAmount": "1.80"
        },
        {
            "feeType": "Power Charge",
            "feeSubType": "Power Charge",
            "rcvblID": "676754676",
            "feeAmount": "611.50",
            "payableAmount": "642.08",
            "billDate": "20260119",
            "billMonth": "208210",
            "days": "17",
            "rebate": "0.00",
            "penalty": "30.58",
            "status": "+5% Penalty",
            "rcvedAmount": "0.00"
        }
    ],
    "paid_upto_bill": [],
    "status": true
}
</code></pre>


  **Sample Response – Paid Bill:**
<pre><code class="json">
{
    "session_id": 19260,
    "consumer_name": "RAJESWARI   GIRI",
    "total_due_amount": "0.00",
    "due_bills": [],
    "paid_upto_bill": {
        "feeType": "Power Charge",
        "feeSubType": "Power Charge",
        "rcvblID": "676755292",
        "feeAmount": "30.00",
        "rcvedAmount": "30.00",
        "payableAmount": "0.00",
        "billDate": "20260119",
        "billMonth": "208210",
        "days": "17",
        "rebate": "0.00",
        "penalty": "1.50",
        "status": "+5% Penalty"
    },
    "status": true
}
</code></pre>

---

## 3. Service Charge

For detailed information regarding applicable service charges, please refer to the document below:

👉 [Service Charge Details](../servicecharge/service-charge.md)

---

## 4. NEA Payment API

**URL:**
```
{{base_url}}/api/servicegroup/commit/nea-v2/
```

**Method:** POST

 **Description:**
Processes payment for NEA bills.

** Request Body:**
<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "session_id": "{{session_id}}",
    "amount": "500",
    "bill_id": "657254846"
}
</code></pre>

  **Success Response:**
<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "SUCCESS",
    "credits_consumed": 40,
    "credits_available": 99991568288.7198,
    "id": 176267
}
</code></pre>

  **Parameters:**
- **session_id**: Received from Detail Fetch API  
- **amount**: Total amount paid by the user  
- **bill_id**:
  - If multiple bills → pass as comma-separated values (`123,231`)  
  - If no bills → do not include this field  

<div style="padding:12px; border-left:4px solid #3b82f6; background-color:#eff6ff; border-radius:6px;">
<strong>Important Notes:</strong>
<ol>
  <li>Users must be allowed to enter the amount manually</li>
  <li>For multiple bills:
    <ul>
      <li>Amount must NOT be less than the oldest bill</li>
      <li>Excess payment is allowed</li>
    </ul>
  </li>
  <li>If no bills are available:
    <ul>
      <li>Do NOT pass <code>bill_id</code></li>
      <li>The amount will be treated as an <strong>advance payment</strong></li>
    </ul>
  </li>
</ol>
</div>

## 5. Get New Consumer ID API

  Description:
Due to NEA system updates, users now require a new consumer ID.  
This API retrieves the updated consumer ID using old SC number and consumer ID.

**URL:**
```
{{base_url}}/api/servicegroup/user-info/nea-v2/
```

**Method:** POST

 **Request Body:**
<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "sc_no": "216.29.013A1",
    "old_consumer_id": "21907",
    "org_name": "balaju"
}
</code></pre>

  **Success Response:**
<pre><code class="json">
{
    "consumer_no": "1001613602",
    "status": true
}
</code></pre>

  **Parameters:**
- **sc_no**: Old SC number  
- **old_consumer_id**: Old consumer ID  
- **org_name**: Organization Value (from Counter API)

<div style="padding:12px; border-left:4px solid #3b82f6; background-color:#eff6ff; border-radius:6px;">
<strong>Important Notes:</strong>
<ul>
  <li>This API is applicable <strong>only for counters where <code>migrated_to_v2 = true</code></strong></li>
  <li>The updated consumer ID is provided by NEA</li>
</ul>
</div>

