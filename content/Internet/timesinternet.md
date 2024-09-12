## 8.6 Times - Internet

**Note:** Below is the list of ISPs under Times and their `service_slug`:

- **8.6.1 Websurfer Internet**: `websurfer-internet`
- **8.6.2 Reliant Technology**: `reliant-technology-v2`
- **8.6.3 Palsnet**: `palsnet`
- **8.6.4 Sky Internet**: `sky-internet`
- **8.6.5 Pathibara Internet**: `pathibara`

### Multi-Step API

The Times Internet API consists of three main steps:

1. **Detail Fetch API**
2. **Package Fetch API**
3. **Payment API**

### 1. Detail Fetch API

**URL:** `{{base_url}}/api/servicegroup/userlist/times/`

**METHOD:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "Account_Token",
  "reference": "Unique Id sent from your side",
  "customer_id": "Customer_ID",
  "service_slug": "service_slug"
}
</code></pre>

**Response:**

<pre><code class="json">
{
  "customer": {
    "cuid": "1000000",
    "first_name": "rajesh",
    "last_name": "lamichhane",
    "status": "active"
  },
  "connection": [
    {
      "username": "rajesh-lamichhane",
      "status": "active"
    },
    {
      "username": "rajesh-lamichhane2",
      "status": "active"
    }
  ],
  "session_id": 2809,
  "status": true
}
</code></pre>

### 2. Package Fetch API

**URL:** `{{base_url}}/api/servicegroup/details/times/`

**METHOD:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "Account_Token",
  "username": "rajesh-lamichhane",
  "session_id": "session_id from user lookup",
  "service_slug": "service_slug",
  "reference": "unique reference id"
}
</code></pre>

**Response:**

<pre><code class="json">
{
  "packages": [
    {
      "package_id": "132",
      "package_name": "10Mbps Half Yearly - Nepalgunj (HALF YEARLY)",
      "amount": 7451
    },
    {
      "package_id": "130",
      "package_name": "10Mbps Monthly - Nepalgunj (MONTHLY)",
      "amount": 1355
    },
    {
      "package_id": "131",
      "package_name": "10Mbps Quarterly - Nepalgunj (QUARTERLY)",
      "amount": 3895
    },
    {
      "package_id": "134",
      "package_name": "10Mbps Yearly - renew- Nepalgu (YEARLY)",
      "amount": 11000
    },
    {
      "package_id": "137",
      "package_name": "15Mbps Half Yearly - Nepalgunj (HALF YEARLY)",
      "amount": 7910
    },
    {
      "package_id": "135",
      "package_name": "15Mbps Monthly - Nepalgunj (MONTHLY)",
      "amount": 1412
    },
    {
      "package_id": "136",
      "package_name": "15Mbps Quarterly - Nepalgunj (QUARTERLY)",
      "amount": 4068
    },
    {
      "package_id": "139",
      "package_name": "15Mbps Yearly - renew- Nepalgu (YEARLY)",
      "amount": 12001
    },
    {
      "package_id": "103",
      "package_name": "15Mbps-Half Yearly (HALF YEARLY)",
      "amount": 5101
    },
    {
      "package_id": "101",
      "package_name": "15Mbps-Monthly (MONTHLY)",
      "amount": 950
    },
    {
      "package_id": "102",
      "package_name": "15Mbps-Quarterly (QUARTERLY)",
      "amount": 2550
    },
    {
      "package_id": "104",
      "package_name": "15Mbps-Yearly (YEARLY)",
      "amount": 10201
    },
    {
      "package_id": "107",
      "package_name": "20Mbps-Half Yearly (HALF YEARLY)",
      "amount": 5700
    },
    {
      "package_id": "105",
      "package_name": "20Mbps-Monthly (MONTHLY)",
      "amount": 950
    },
    {
      "package_id": "106",
      "package_name": "20Mbps-Quarterly (QUARTERLY)",
      "amount": 2851
    },
    {
      "package_id": "108",
      "package_name": "20Mbps-Yearly (YEARLY)",
      "amount": 11400
    },
    {
      "package_id": "111",
      "package_name": "30Mbps-Half Yearly (HALF YEARLY)",
      "amount": 7500
    },
    {
      "package_id": "109",
      "package_name": "30Mbps-Monthly (MONTHLY)",
      "amount": 1250
    },
    {
      "package_id": "110",
      "package_name": "30Mbps-Quarterly (QUARTERLY)",
      "amount": 3750
    },
    {
      "package_id": "112",
      "package_name": "30Mbps-Yearly (YEARLY)",
      "amount": 15000
    },
    {
      "package_id": "115",
      "package_name": "40Mbps-Half Yearly (HALF YEARLY)",
      "amount": 9000
    },
    {
      "package_id": "119",
      "package_name": "40Mbps-Half Yearly-Nepalgunj (HALF YEARLY)",
      "amount": 7800
    },
    {
      "package_id": "113",
      "package_name": "40Mbps-Monthly (MONTHLY)",
      "amount": 1501
    },
    {
      "package_id": "141",
      "package_name": "40Mbps-Monthly @ 1000-R (MONTHLY)",
      "amount": 1000
    },
    {
      "package_id": "117",
      "package_name": "40Mbps-Monthly-Nepalgunj (MONTHLY)",
      "amount": 1300
    },
    {
      "package_id": "118",
      "package_name": "40Mbps-Quarterly-Nepalgunj (QUARTERLY)",
      "amount": 3900
    },
    {
      "package_id": "120",
      "package_name": "40Mbps-Yearly-Nepalgunj (YEARLY)",
      "amount": 14501
    },
    {
      "package_id": "127",
      "package_name": "5Mbps Half Yearly - Nepalgunj (HALF YEARLY)",
      "amount": 4740
    },
    {
      "package_id": "125",
      "package_name": "5Mbps Monthly Old - Nepalgunj (MONTHLY)",
      "amount": 790
    },
    {
      "package_id": "126",
      "package_name": "5Mbps Quarterly - Nepalgunj (QUARTERLY)",
      "amount": 2201
    },
    {
      "package_id": "129",
      "package_name": "5Mbps Yearly - renew- Nepalgun (YEARLY)",
      "amount": 5901
    }
  ],
  "session_id": 2809,
  "status": true
}
</code></pre>

### 3. Payment API

**URL:** `{{base_url}}/api/servicegroup/commit/times/`

**METHOD:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "Account_Token",
  "session_id": "session_id from user lookup",
  "amount": "Package Amount from package fetch API",
  "package_id": "package ID from package fetch API"
}
</code></pre>

**Response:**

<pre><code class="json">
{
  "status": true,
  "state": "Success",
  "message": "Successfully Completed Transaction",
  "extra_data": {},
  "detail": "Success",
  "credits_consumed": 790.0,
  "credits_available": 9999378747.53,
  "id": 42353
}
</code></pre>
