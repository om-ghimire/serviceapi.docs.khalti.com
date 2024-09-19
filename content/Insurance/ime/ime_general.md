# IME General Insurance

## Overview

The IME General Insurance API provides a structured approach to handle insurance-related operations, including fetching details of various insurance types and processing payments for those insurance policies.

### **Type: Multi Step API**

---

### 1. **Detail API**

**Request URL:** `{{base_url}}/api/servicegroup/info/ime-general-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "policy_type": [
        { "label": "Endorsement", "value": "1" },
        { "label": "New", "value": "2" },
        { "label": "Renewal", "value": "3" }
    ],
    "insurance_type": [
        { "label": "Motor/Vehicle Insurance", "value": "1" },
        { "label": "Property Insurance", "value": "2" },
        { "label": "Engineering Insurance", "value": "3" },
        { "label": "Group Personal Accidental Insurance", "value": "4" },
        { "label": "Money Insurance", "value": "5" },
        { "label": "Banker's Blanket Insurance", "value": "6" },
        { "label": "Personal Accidental Insurance", "value": "7" },
        { "label": "Professional Indemnity Insurance", "value": "8" },
        { "label": "Cash In Transit Insurance", "value": "9" },
        { "label": "Public Liability Insurance", "value": "10" },
        { "label": "Medi Claim Insurance", "value": "11" },
        { "label": "Travel Insurance", "value": "12" },
        { "label": "Cash Counter Insurance", "value": "13" },
        { "label": "Gold Insurance", "value": "14" },
        { "label": "Press Accident Insurance", "value": "15" },
        { "label": "Adventure Sports Insurance", "value": "16" },
        { "label": "Tracking Insurance", "value": "17" },
        { "label": "Cyber Insurance", "value": "18" },
        { "label": "Critical Illness Insurance", "value": "19" },
        { "label": "Marine Insurance", "value": "20" },
        { "label": "Micro/Agriculture Insurance", "value": "21" }
    ],
    "branches": [
        { "label": "Head Office", "value": "1" },
        { "label": "Pokhara", "value": "2" },
        { "label": "Butwal", "value": "3" },
        { "label": "Narayangadh", "value": "4" },
        { "label": "Nepalgunj", "value": "5" },
        { "label": "Birgunj", "value": "6" },
        { "label": "Dhangadhi", "value": "7" },
        { "label": "Banepa", "value": "8" },
        { "label": "Biratnagar", "value": "9" },
        { "label": "Janakpur", "value": "10" },
        { "label": "Hetauda", "value": "11" },
        { "label": "Okhaldhunga", "value": "12" },
        { "label": "Bardibas", "value": "13" },
        { "label": "Solukhumbu", "value": "14" },
        { "label": "Gongabu", "value": "15" },
        { "label": "Kalanki", "value": "16" },
        { "label": "Koteshwor", "value": "17" },
        { "label": "Bhaktapur", "value": "18" },
        { "label": "Bhairahawa", "value": "19" },
        { "label": "Dolakha", "value": "20" },
        { "label": "Dang", "value": "21" },
        { "label": "Jawalakhel", "value": "22" },
        { "label": "Aabukhaireni", "value": "23" },
        { "label": "Birtamod", "value": "24" },
        { "label": "Baglung", "value": "25" },
        { "label": "Kawasoti", "value": "26" },
        { "label": "New Road", "value": "27" },
        { "label": "Surkhet", "value": "28" },
        { "label": "Dhading", "value": "29" },
        { "label": "Manthali", "value": "30" },
        { "label": "Boudha", "value": "31" },
        { "label": "Itahari", "value": "32" },
        { "label": "Damak", "value": "33" },
        { "label": "Teku", "value": "34" },
        { "label": "Tulsipur", "value": "35" },
        { "label": "Nuwakot", "value": "36" },
        { "label": "Syangja", "value": "37" },
        { "label": "Tandi", "value": "38" },
        { "label": "Dadeldhura", "value": "39" },
        { "label": "Lahan", "value": "40" },
        { "label": "Kirtipur", "value": "41" },
        { "label": "Simara", "value": "42" },
        { "label": "Mahendranagar", "value": "43" },
        { "label": "Damauli", "value": "44" },
        { "label": "Ilam", "value": "45" }
    ]
}
</code></pre>

---

### 2. **Payment API**

**Request URL:** `{{base_url}}/api/use/ime-general-insurance/`

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
    "token": "token",
    "policy_type": "Endorsement",
    "insurance_type": "Property Insurance",
    "branch": "Pokhara",
    "full_name": "test test",
    "address": "address",
    "mobile_number": "9841111111",
    "policy_description": "Description",
    "debit_note_no": "123465789",
    "bill_no": "12346589",
    "email": "user_email_id",
    "amount": "10",
    "reference": "Unique Reference"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "status": true,
    "state": "Queued",
    "detail": "Transaction Queued",
    "message": "Your operation is in queue.",
    "credits_consumed": 10.0,
    "credits_available": 9999633548.47,
    "extra_data": {
        "policy_type": "Endorsement",
        "insurance_type": "Property Insurance",
        "branch": "Pokhara",
        "full_name": "test test",
        "address": "test test",
        "mobile_number": "9841111111",
        "policy_description": "test test",
        "debit_note_no": "123465789",
        "bill_no": "12346589",
        "email": "ressrew"
    },
    "id": 34849
}
</code></pre>
