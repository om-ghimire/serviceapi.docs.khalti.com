# **Subisu New**

**Multistep API**

**NOTE:**

* If there is an outstanding amount greater than 0, users can choose to pay either the outstanding amount or their package payment. Users can also pay for their package if the outstanding amount is greater than 0.
* When fetching details, there are four different responses based on the user's plans: TV only, internet only, TV + internet, and Combo.
* Users with TV can have either a Single STB or multiple STBs. This applies to TV only and Internet + TV users.
* Payment parameters change based on the type of payment: Outstanding payment, TV payment, Internet payment, or Combo offer payment.

## 1. Detail Fetch API 

**URL:** {{base_url}}/api/servicegroup/details/subisu/

**Service Params:**

<pre><code class="json">
{  
  "token": "token-provided",  
  "reference": "unique-reference",  
  "username": "username"  
}
</code></pre>

### **Response:**

**Note:** 

* There are four different `plan_type` values, and responses vary based on `plan_type`. 
* TV may have either a single STB or multiple STBs.

**Types of Response:**

1. **Response of `plan_type`: "internet"**

   **Test User:** `khaltiinternet`

   <pre><code class="json">
   {  
     "customer_name": "Northbound Test Khalti",  
     "address": "Baluwatar",  
     "current_plan_name": "Internet Northbound",  
     "user_id": "khaltiinternet",  
     "outstanding_amount": "0.00",  
     "expiry_date": "2023-08-25T23:59:59",  
     "mobile_no": "9100000000",  
     "onu_id": null,  
     "partner_name": "Selfcare Test 1",  
     "plan_detail_list": {  
       "plan_detail_list": {  
         "internet_plan_details": [  
           {  
             "amount": 10,  
             "plan_name": "Internet Northbound",  
             "description": "10.00",  
             "primary_speed": "0",  
             "volume_quota": "0",  
             "validity": "30 Days"  
           },  
           {  
             "amount": 10,  
             "plan_name": "Internet Northbound",  
             "description": "10.00",  
             "primary_speed": "4096",  
             "volume_quota": null,  
             "validity": "30 Days"  
           },  
           {  
             "amount": 4000,  
             "plan_name": "10Mbps 12Months BPKIHS",  
             "description": "4000.00",  
             "primary_speed": "10240",  
             "volume_quota": null,  
             "validity": "360 Days"  
           },  
           {  
             "amount": 10,  
             "plan_name": "Selfcare Renew eSewa",  
             "description": "10.00",  
             "primary_speed": "20480",  
             "volume_quota": null,  
             "validity": "1 Days"  
           },  
           {  
             "amount": 1,  
             "plan_name": "Selfcare Renew IPS & Card",  
             "description": "1.00",  
             "primary_speed": "20480",  
             "volume_quota": null,  
             "validity": "1 Days"  
           }  
         ]  
       },  
       "plan_type": "internet"  
     },  
     "session_id": 9017,  
     "status": true  
   }
   </code></pre>

2. **Response of `plan_type`: "combo offer"**

   **Test User:** `khaltioffer`

   <pre><code class="json">
   {  
     "customer_name": "Northbound Test Khalti",  
     "address": "khaltioffer",  
     "current_plan_name": "Offer Test Data",  
     "user_id": "khaltioffer",  
     "outstanding_amount": "0.00",  
     "expiry_date": "2023-08-29T23:59:59",  
     "mobile_no": "9100000000",  
     "tv_plan_list": {  
       "tv_plan_details": [  
         {  
           "current_video_plan_name": "Offer Test Video",  
           "stb": "ABCCD10BBBFC942B",  
           "expiry_date": "2023-08-29T23:59:59"  
         }  
       ]  
     },  
     "onu_id": null,  
     "partner_name": "Selfcare Test 1",  
     "plan_detail_list": {  
       "plan_detail_list": [  
         {  
           "validity": "1 Months",  
           "offer_name": "Combo Offer Test 2",  
           "offer_id": "4237",  
           "amount": 10,  
           "combo_plan_details": [  
             {  
               "plan_type": "Data",  
               "service_media": "FTTH",  
               "activation_date": "2023-08-30T00:00:00",  
               "expiry_date": "2023-09-29T00:00:00",  
               "allow_to_renew": "false",  
               "service_media_id": "11952",  
               "stb_id": null,  
               "is_primary": "false",  
               "expiry_date_string": "29-Sep-2023",  
               "activation_date_string": "30-Aug-2023"  
             },  
             {  
               "plan_type": "Video",  
               "service_media": "Clear TV(DTV)",  
               "activation_date": "2023-08-30T00:00:00",  
               "expiry_date": "2023-09-29T00:00:00",  
               "allow_to_renew": "false",  
               "service_media_id": "11956",  
               "stb_id": "780784",  
               "is_primary": "true",  
               "expiry_date_string": "29-Sep-2023",  
               "activation_date_string": "30-Aug-2023"  
             }  
           ]  
         }  
       ],  
       "plan_type": "combo offer"  
     },  
     "session_id": 9018,  
     "status": true  
   }
   </code></pre>

3. **Response of `plan_type`: "tv"**

   **Test User:** `paypoint_video`

   <pre><code class="json">
   {  
     "customer_name": "Paypoint Video",  
     "address": "Baluwatar",  
     "user_id": "paypoint_video",  
     "outstanding_amount": "0.00",  
     "expiry_date": null,  
     "mobile_no": "9100000000",  
     "tv_plan_list": {  
       "tv_plan_details": [  
         {  
           "current_video_plan_name": "Video Tests Plan 1M",  
           "stb": "sample5",  
           "expiry_date": "2023-06-17T23:59:59"  
         },  
         {  
           "current_video_plan_name": "Mobile API DTV CHILD - TEST",  
           "stb": "TEST0001",  
           "expiry_date": "2023-06-17T23:59:59"  
         }  
       ]  
     },  
     "onu_id": null,  
     "partner_name": "Selfcare Test 1",  
     "plan_detail_list": {  
       "plan_detail_list": [  
         {  
           "stb": "sample5",  
           "tv_plan_details": [  
             {  
               "amount": 10,  
               "plan_name": "Video Tests Plan 1M",  
               "validity": "30 Days"  
             }  
           ]  
         }  
       ],  
       "plan_type": "tv"  
     },  
     "session_id": 9019,  
     "status": true  
   }
   </code></pre>

4. **Response of `plan_type`: "internet + tv"**

   **Test User:** `khaltivideo`

   <pre><code class="json">
   {  
     "customer_name": "Khalti Video Plan",  
     "address": "Baluwatar",  
     "current_plan_name": "Selfcare Renew eSewa",  
     "user_id": "khaltivideo",  
     "outstanding_amount": "0.00",  
     "expiry_date": "2023-07-01T23:59:59",  
     "mobile_no": "9100000000",  
     "tv_plan_list": {  
       "tv_plan_details": [  
         {  
           "current_video_plan_name": "Video offer child tests",  
           "stb": "Sample 11",  
           "expiry_date": "2023-07-21T23:59:59"  
         },  
         {  
           "current_video_plan_name": "Video Tests Plan 1M",  
           "stb": "ABCC2C1D07B01A20",  
           "expiry_date": "2023-08-21T23:59:59"  
         }  
       ]  
     },  
     "onu_id": null,  
     "partner_name": "Selfcare Test 1",  
     "plan_detail_list": {  
       "plan_detail_list": {  
         "internet_details": {  
           "internet_plan_details": [  
             {  
               "amount": 10,  
               "plan_name": "Selfcare Renew eSewa",  
               "description": "10.00",  
               "primary_speed": "0",  
               "volume_quota": "0",  
               "validity": "1 Days"  
             },  
             {  
               "amount": 10,  
               "plan_name": "Internet Northbound",  
               "description": "10.00",  
               "primary_speed": "4096",  
               "volume_quota": null,  
               "validity": "30 Days"  
             },  
             {  
               "amount": 4000,  
               "plan_name": "10Mbps 12Months BPKIHS",  
               "description": "4000.00",  
               "primary_speed": "10240",  
               "volume_quota": null,  
               "validity": "360 Days"  
             },  
             {  
               "amount": 10,  
               "plan_name": "Selfcare Renew eSewa",  
               "description": "10.00",  
               "primary_speed": "20480",  
               "volume_quota": null,  
               "validity": "1 Days"  
             },  
             {  
               "amount": 1,  
               "plan_name": "Selfcare Renew IPS & Card",  
               "description": "1.00",  
               "primary_speed": "20480",  
               "volume_quota": null,  
               "validity": "1 Days"  
             }  
           ]  
         },  
         "tv_details": [  
           {  
             "stb": "ABCC2C1D07B01A20",  
             "tv_plan_details": [  
               {  
                 "amount": 10,  
                 "plan_name": "Video Tests Plan 1M",  
                 "validity": "30 Days"  
               }  
             ]  
           },  
           {  
             "stb": "ABCC2C1D07B01A20",  
             "tv_plan_details": [  
               {  
                 "amount": 10,  
                 "plan_name": "Video Tests Plan 1M",  
                 "validity": "30 Days"  
               }  
             ]  
           },  
           {  
             "stb": "Sample 11",  
             "tv_plan_details": [  
               {  
                 "amount": 3,  
                 "plan_name": "Video offer child tests",  
                 "validity": "30 Days"  
               }  
             ]  
           },  
           {  
             "stb": "Sample 11",  
             "tv_plan_details": [  
               {  
                 "amount": 3,  
                 "plan_name": "Video offer child tests",  
                 "validity": "30 Days"  
               }  
             ]  
           }  
         ]  
       },  
       "plan_type": "internet + tv"  
     },  
     "session_id": 9020,  
     "status": true  
   }
   </code></pre>

## 2. Payment API

**Request URL:** {{base_url}}/api/servicegroup/commit/subisu/

**Request Method:** POST

Outstanding amount is the due amount. Users can choose to pay the outstanding amount or the package amount. Parameters change based on the type of payment:

1. **Outstanding Payment**  
   If `outstanding_amount` > 0, users can pay the outstanding amount. This works for all plan types: internet, combo offer, TV, and internet + TV.

   **Service Params for Outstanding Payment:**

   <pre><code class="json">
   {  
     "token": "provided_token",  
     "session_id": Obtained from detail fetch API,  
     "amount": "amount",  // amount from detail step  
     "renew_type": "outstanding_payment"  
   }
   </code></pre>

2. **TV Payment**  
   When fetching details, users must select one STB if there are multiple STBs. This works for plan types: TV and internet + TV.

   **Service Params for TV Payment:**

   <pre><code class="json">
   {  
     "token": "provided_token",  
     "session_id": Obtained from detail fetch API,  
     "amount": "amount",  // amount from detail fetch API  
     "offer_name": "offer_name",  // plan_name from detail step  
     "stb": "stb"  // STB from detail fetch API  
   }
   </code></pre>

3. **Internet Payment**  
   This works for plan types: TV and internet + TV.

   **Service Params for Internet Payment:**

   <pre><code class="json">
   {  
     "token": "provided_token",  
     "session_id": Obtained from detail fetch API,  
     "amount": "amount",  // amount from detail step  
     "offer_name": "offer_name"  // plan_name from detail step  
   }
   </code></pre>

4. **Offer Payment**  
   This works for the combo offer plan type.

   **Service Params for Offer Payment:**

   <pre><code class="json">
   {  
     "token": "provided_token",  
     "session_id": Obtained from detail fetch API,  
     "amount": "amount",  // amount from detail step  
     "offer_name": "offer_name"  // offer_name from detail step  
   }
   </code></pre>

### **Success Response:**

<pre><code class="json">
{  
  "status": true,  
  "state": "Success",  
  "message": "Successfully Completed Transaction",  
  "extra_data": {},  
  "detail": "2531",  
  "credits_consumed": 1232,  
  "credits_available": 2460415608.4800014,  
  "id": 64146  
}
</code></pre>

### **Failed Response:**

1. **If the user has no outstanding amount**

   <pre><code class="json">
   {  
     "status": false,  
     "error_code": "4000",  
     "message": "Can't fulfill request",  
     "error": "client_error",  
     "details": "No outstanding dues.",  
     "error_data": {},  
     "state": "Error"  
   }
   </code></pre>

2. **If the user has already purchased the package**

   <pre><code class="json">
   {  
     "status": false,  
     "error_code": "4000",  
     "message": "Can't fulfill request",  
     "error": "client_error",  
     "details": "Future plan is already exist.",  
     "error_data": {},  
     "state": "Error"  
   }
   </code></pre>

3. **Invalid offer name and amount**

   <pre><code class="json">
   {  
     "status": false,  
     "error_code": "1011",  
     "message": "Validation error",  
     "error": "validation_error",  
     "details": {  
       "offer_name": "Offer_name does not match with amount!"  
     },  
     "error_data": {},  
     "state": "Error"  
   }
   </code></pre>
