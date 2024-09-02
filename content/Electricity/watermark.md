# **Watermark Electricity**

**Note:** Below is the list of electricity services under Watermark Electricity and their respective `service_slug`:

### WaterMark Electricity Slugs
| Name                                                            | service_slug                                  |
|-----------------------------------------------------------------|-----------------------------------------------|
| Badagaun Samudayik Gramin Bidyut                               | badagaun-samudayik-gramin-bidyut              |
| Bhimad Electricity                                             | bhimad-electricity                            |
| Bungdikali Samudayik Bidhutikaran                              | bungdikali-samudayik-bidhutikaran             |
| Chhongpulunglaparata Khola Sana                                | chhongpulunglaparata-khola-sana               |
| Deep Jyoti Community Electricity                               | deep-jyoti-community-electricity              |
| Gramin Bidhut                                                  | gramin-bidhut                                 |
| Gramin Prubadhar                                               | gramin-prubadhar                              |
| Halesi Community Rural Electricity                              | halesi-community-rural-electricity            |
| Handikhola Ditiya Gramin                                       | handikhola-ditiya-gramin                      |
| Kachanapur Gramin Bidhut                                        | kachanapur-gramin-bidhut                      |
| Kalikapur Gramin Community Electricity                         | kalikapur-gramin-community-electricity        |
| Khumbu Bijuli                                                   | khumbu-bijuli                                |
| Kusum Community Electricity                                    | kusum-community-electricity                   |
| Maha Shivashakti Gramin Bidhyut                                | maha-shivashakti-gramin-bidhyut              |
| Marsyandi Electricity                                           | marsyandi-electricity                         |
| Matribhumi Gramin Vidhyut Sahakari Sanstha                     | matribhumi-gramin-vidhyut-sahakari-sanstha    |
| Morang Community Electricity                                    | morang-community-electricity                  |
| Nagre Gagarche Gramin Eletricity                                | nagre-gagarche-gramin-eletricity              |
| Nawadip Samudayik Bidhut                                        | nawadip-samudayik-bidhut                     |
| Pragatinagar Electricity V2                                     | pragatinagar-electricity-v2                  |
| Purandhara Samudayik Bidyut                                    | purandhara-samudayik-bidyut                  |
| Roshani Gramin Bidhyut                                         | roshani-gramin-bidhyut                       |
| Samudayik Bidhut Dhorfirdi                                     | samudayik-bidhut-dhorfirdi                   |
| Samudayik Bidhut Upabhokta Samiti, Syangja                     | samudayik-bidhut-upabhokta-samiti-syangja   |
| Samudayik Gramin Bidhutikaran Upabhokta Samiti                 | samudayik-gramin-bidhutikaran-upabhokta-samiti|
| Samudayik Gramin Bidhut Panchkhal                              | samudayik-gramin-bidhut-panchkhal            |
| Samudayik Gramin Bidyut Sahakari                               | samudayik-gramin-bidyut-sahakari             |
| Shankhamul Gramin Bidhutikaran                                 | shankhamul-gramin-bidhutikaran               |
| Shishaghat Community Rural Electricity                          | shishaghat-community-rural-electricity        |
| Shree Barpipal Chautari Gramin Vidhut                          | shree-barpipal-chautari-gramin-vidhut        |
| Shree Behada Baba Gramin Bidhyut                               | shree-behada-baba-gramin-bidhyut            |
| Shree Gauriganga Gramin Bidhut                                 | shree-gauriganga-gramin-bidhut              |
| Shree Jay Maa Durga Gramin Vidhut Sahakari Sanstha              | shree-jay-maa-durga-gramin-vidhut-sahakari-sanstha|
| Shree Maa Badimalika Gramin Bidhut Sahakari                    | shree-maa-badimalika-gramin-bidhut-sahakari |
| Shree Manusmriti Gramin Vidhut                                  | shree-manusmriti-gramin-vidhut              |
| Shree Mohanyal Gramin Vidhut                                    | shree-mohanyal-gramin-vidhut                |
| Shree Naba Pasupati Gramin Bidhut                               | shree-naba-pasupati-gramin-bidhut           |
| Shree Netra Jyoti Gramin Vidhut                                 | shree-netra-jyoti-gramin-vidhut             |
| Shree Pragatishil Gramin Vidhut                                 | shree-pragatishil-gramin-vidhut             |
| Shree Prithivi Bahuudhyasyiya Bidhut Upobhokta Samiti           | shree-prithivi-bahuudhyasyiya-bidhut-upobhokta-samiti|
| Shree Shiv Shaktiman Gramin Vidhut                              | shree-shiv-shaktiman-gramin-vidhut         |
| Shree Siddhababa Gramin Bidhut                                  | shree-siddhababa-gramin-bidhut              |
| Shree Subha Laxmi Gramin Bidhyut                                | shree-subha-laxmi-gramin-bidhyut           |
| South Lalitpur Electricity                                     | south-lalitpur-electricity                  |
| Swargadwari Community Electricity                               | swargadwari-community-electricity            |
| Thalachowk Bidhut                                              | thalachowk-bidhut                            |
| Thoksila Electricity                                           | thoksila-electricity                         |

##

**Type: Multi-Step API**

### 1. **Detail Fetch API**

**Request URL:** {{base_url}}/api/servicegroup/details/watermark-electricity/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "{{token}}",
  "customer_code": "590-11",
  "reference": "unique_reference",
  "service_slug": "service_slug"
}
</code></pre>

**Response:**

<pre><code class="json">
{
    "customer_code": "590-11",
    "customer_name": "Kedar Nath Timilsina",
    "address": "Devichaur-04",
    "meter_no": "11086508",
    "zone": "Devichaur(01)",
    "ward": "01-01",
    "type": "Domestic",
    "advance_amount": 82.5,
    "total_due_amount": 330.0,
    "due_bills": [
        {
            "description": "Tariff of 2078-Baisakh",
            "date": "2078-1-9",
            "amount": 257.0
        },
        {
            "description": "Penal of 2078-Baisakh",
            "date": "2078-1-9",
            "amount": 64.25
        },
        {
            "description": "Demand Fee",
            "date": "2078-1-9",
            "amount": 65.0
        },
        {
            "description": "Penal of 2078-Baisakh Demand Fee",
            "date": "2078-1-9",
            "amount": 16.25
        },
        {
            "description": "Service Charge",
            "date": "2078-1-9",
            "amount": 10.0
        },
        {
            "description": "Penal of 2078-Baisakh Service Charge",
            "date": "2078-1-9",
            "amount": 0.0
        }
    ],
    "session_id": 442,
    "status": true
}
</code></pre>

**Fields:**

- **customer_code**: The unique code assigned to the customer.
- **customer_name**: The name of the customer.
- **address**: The address of the customer.
- **meter_no**: The meter number for the electricity connection.
- **zone**: The zone where the customer is located.
- **ward**: The ward within the zone.
- **type**: The type of service (e.g., Domestic).
- **advance_amount**: The amount of advance payment made.
- **total_due_amount**: The total amount due for payment.
- **due_bills**: An array of due bills, including:
  - **description**: The description of the charge.
  - **date**: The date of the bill.
  - **amount**: The amount of the bill.
- **session_id**: The unique session ID for the transaction.
 

### 2. **Payment API**

**Request URL:** {{base_url}}/api/servicegroup/commit/watermark-electricity/

**Request Method:** POST

**Service Params:**

<pre><code class="json">
{
  "token": "{{token}}",
  "reference": "unique_reference",
  "session_id": "btained from previous API",
  "amount": "obtained from previous API 'total_due_amount'"
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
    "credits_consumed": 330.0,
    "credits_available": "xxxx",
    "id": 107598
}
</code></pre>

**Fields:**

 
- **state**: The state of the transaction (`Success`).
- **message**: A message indicating the result of the transaction (`Successfully Completed Transaction`).
- **extra_data**: Any additional data related to the transaction.
- **detail**: Additional details about the payment, including:
  - **detail**: A message indicating the success of the payment (`Success`).
- **credits_consumed**: The total credits consumed for this transaction.
- **credits_available**: The total credits available after this transaction.
- **id**: The unique ID associated with the transaction.

