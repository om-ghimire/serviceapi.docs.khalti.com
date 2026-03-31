# NEA (Nepal Electricity Authority) API Updated Documentation

## 1. Get Counters API

**URL:**
```
{{base_url}}/api/servicegroup/counters/nea-v2/
```

### Description:
Fetches the list of all available counters.

### Response Fields:
- **name**: Name of the counter  
- **migrated_to_v2**: Determines whether to use NEA V1 or NEA V2  
- **value**: Value to be passed in the next API  

### Logic:
- If `migrated_to_v2 = false` → Use **NEA V1**
- If `migrated_to_v2 = true` → Use **NEA V2**

---

## 2. NEA V2 Detail Fetch API

**URL:**
```
{{base_url}}/api/servicegroup/details/nea-v2/
```

**Method:** POST

### Request Body:
```json
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "request_no": "1001595737",
    "confirm_type": "E",
    "confirm_id_type": "CN"
}
```

### Parameters:
- **request_no**: New consumer number (provided by NEA)
- **confirm_type**: Always `"E"` (Energy Charge) *(may support multiple values in future)*
- **confirm_id_type**: Always `"CN"` (Consumer Number) *(may support multiple values in future)*

## 3. Service Charge

For detailed information regarding applicable service charges, please refer to the following document:

👉 [Service Charge Details](../servicecharge/service-charge.md)

---

## 4. NEA Payment API

**URL:**
```
{{base_url}}/api/servicegroup/commit/nea-v2/
```

**Method:** POST

### Request Body:
```json
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "session_id": "{{session_id}}",
    "amount": "500",
    "bill_id": "657254846"
}
```

### Parameters:
- **session_id**: From Detail Fetch API  
- **amount**:  Total amount Paid by user
- **bill_id**:
    - If multiple bills → pass as comma-separated values (`123,231`)
    - If no bills → do not pass this field

### Important Notes:
1. User must be allowed to enter amount manually  
2. In case of multiple bills:
    - Amount must NOT be less than the oldest bill  
    - User can pay excess amount  
3. In case of no bills:
    - Do NOT pass `bill_id`
    - Amount will be treated as **advance payment**

---

## 5. Get New Consumer ID API

### Description:
Since NEA updated their system, users now require a **new consumer ID**.  
This API helps fetch the updated consumer ID using old Sc no and consumer No.

**URL:**
```
{{base_url}}/api/servicegroup/user-info/nea-v2/
```

**Method:** POST

### Request Body:
```json
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "sc_no": "216.29.013A1",
    "old_consumer_id": "21907",
    "org_name": "balaju"
}
```

### Parameters:
- **sc_no**: Old SC number  
- **old_consumer_id**: Old consumer ID  
- **org_name**: New organization name (from Counter API)

### Important Notes:
- This API works **only for counters where `migrated_to_v2 = true`**
- Updated consumer ID is provided by NEA
