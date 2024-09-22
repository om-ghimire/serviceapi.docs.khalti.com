# Broadlink 

**Introduction:**

This documentation provides the APIs to fetch details and make payments for Broadlink internet users.

## Broadlink Payment Types:

### Outstanding Payment
Users who inform Broadlink to activate their internet and generate an invoice for the payable amount. In this case, you will not find the “packages” key in the response. Use the “amount” key for payment and skip the getDiscount API before proceeding to the commit API.

- **Example Customer ID:** 53905

### Package Payment
Users can choose a package. The “amount” key in the detail API will be 0 in this case. Use the “packages” key for package details and proceed to the checkDiscount API to get the final discounted amount.

- **Example Customer ID:** 47531

## 1. Broadlink Detail Fetch API

- **Request URL:** `{{base_url}}/api/servicegroup/details/broadlink/`
- **Request Method:** POST

### Service Params

<pre><code class="json">
{
    "token": "token",
    "customer_id": 53905,
    "reference": "Broadlink"
}
</code></pre>

### Response for Outstanding Payment

<pre><code class="json">
{
    "name": "sujansir home",
    "email": "sujan@broadlink.com",
    "mobile_no": "9801011844",
    "customer_id": "53905",
    "amount": "1129",
    "invoice_no": "343327",
    "session_id": 5,
    "status": true
}
</code></pre>

### Response for Package Payment

<pre><code class="json">
{
    "name": "sujansir home",
    "mobile_no": "9801011844",
    "customer_id": "53905",
    "email": "sujan@broadlink.com",
    "amount": 0,
    "invoice_no": 0,
    "packages": [
        {
            "package": "Supernet 10 mbps@999 MID BasePlan",
            "package_id": "4",
            "package_sub_id": "4",
            "amount": "1129"
        },
        {
            "package": "Supernet 20 mbps@1499 KTM BasePlan",
            "package_id": "16",
            "package_sub_id": "16",
            "amount": "1694"
        },
        {
            "package": "Supernet 20 mbps@1499 KTM BasePlan",
            "package_id": "16",
            "package_sub_id": "258",
            "amount": "17684"
        },
        {
            "package": "Supernet 20 mbps@1499 KTM BasePlan",
            "package_id": "16",
            "package_sub_id": "259",
            "amount": "9553"
        },
        {
            "package": "Doen OLD 5mbps@599 EAST BasePlan",
            "package_id": "35",
            "package_sub_id": "35",
            "amount": "677"
        },
        {
            "package": "30 mbps Dhamaka - OV",
            "package_id": "158",
            "package_sub_id": "350",
            "amount": "13560"
        },
        {
            "package": "test icon",
            "package_id": "224",
            "package_sub_id": "528",
            "amount": "0"
        }
    ],
    "session_id": 6,
    "status": true
}
</code></pre>

---

## 2. Broadlink Get Discount API

- **Request URL:** `{{base_url}}/api/servicegroup/get_discounted_amount/broadlink/`
- **Request Method:** POST

### Service Params

<pre><code class="json">
{
    "token": "token",
    "session_id": 5,
    "package_id": 4,
    "package_sub_id": 4
}
</code></pre>

### Response

<pre><code class="json">
{
    "status": true,
    "detail": {
        "amount": "1129.00",
        "package": "Supernet 10 mbps@999 MID BasePlan"
    }
}
</code></pre>

---

## 3. Broadlink Commit API

- **Request URL:** `{{base_url}}/api/servicegroup/commit/broadlink/`
- **Request Method:** POST

### Service Params

<pre><code class="json">
{
    "token": "token",
    "session_id": 5,
    "amount": 1129
}
</code></pre>

### Response

<pre><code class="json">
{
    "status": true,
    "state": "Success",
    "message": "Successfully Completed Transaction",
    "extra_data": {},
    "detail": "Successful Payment",
    "credits_consumed": 1129.0,
    "credits_available": 95727.0,
    "id": 5373
}
</code></pre>

