# **Neco Insurance API**

**Type**: Multi Step API

## Insurance Policy Categories

**Request URL**: {{base_url}}/api/servicegroup/details/neco-insurance/

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
  "token": "Token",
  "insurance_slug": "neco-insurance"
}
</code></pre>

**Regex**:

<pre><code class="json">
[
  {
    "name": "Mobile",
    "slug": "",
    "pattern": "([9][678][0-6][0-9]{7})",
    "error_message": "Invalid mobile number"
  }
]
</code></pre>

**Response**:

<pre><code class="json">
{
  "category_list": {
    "neco-insurance": [
      "Cardamon Agr",
      "AGR / CAD GROUP",
      "Agriculture",
      "AGR / CAT GROUP",
      "AGR / POU GROUP",
      "AGR / CRP GROUP",
      "AGR / FSH GROUP",
      "Cattle agr",
      "Poultry agr",
      "Fish agr",
      "Rice agr",
      "Vegetable agr",
      "Potato agr",
      "Fruit agr",
      "tmcy (motorcycle)",
      "tpc (private vehicle)",
      "tcvb (Public Bus)",
      "tcvo (Other)",
      "tcvt (Truck and Tanker)",
      "tcvv (Private Bus)",
      "tcvx (Taxi)",
      "Personnel Accident(Micro)",
      "Health Insurance(Micro)",
      "Crop",
      "Bee agr",
      "AGR / BEE GROUP",
      "Mushroom agr"
    ]
  },
  "status": true
}
</code></pre>

## Neco Insurance Payment

**Request URL**: {{base_url}}/api/servicegroup/commit/neco-insurance/

**Request Method**: POST

**Service Params**:

<pre><code class="json">
{
  "token": "Account_Token",
  "policy_type": "Fresh OR Renew OR",
  "customer_name": "RamLal",
  "policy_category": "Any one value from categories above",
  "amount": 100.0,
  "reference": "unique identifier for each request",
  "policy_number": "Optional Field | 12",
  "mobile_number": "9843664612",
  "service_name": "neco-insurance",
  "insurance_slug": "insurance_slug_from_search_step"
}
</code></pre>

**Response**:

<pre><code class="json">
{
  "credits_available": 681649.199999999,
  "message": "Your operation is in queue.",
  "state": "Queued",
  "status": true,
  "credits_consumed": 1,
  "id": 442
}
</code></pre>
