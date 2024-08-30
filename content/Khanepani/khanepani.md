## **6\. Khanepani** 

Type: Multi Step API  
**Request: POST**  
Khanepani Counters 

**URL : [{{base_url}}](https://services.khalti.com/api/servicegroup/details/worldlink/)/api/servicegroup/counters/khanepani/** 

Service Params   
{  
	“token”: \<token\>  
}

Regex:

\[

* {  
  * name: "Customer Code",  
  * slug: "",  
  * pattern: "(\[a-zA-Z0-9\_\\-\]+)",  
  * error\_message: "Invalid Customer Code",  
* }

\]

Example  
\<?php 

$url \= "{{base_url}}/api/servicegroup/counters/khanepani/";   
$args \= http\_build\_query(array(   
		'token' \=\> '\<token-provided\>'  
)); 

\# Make the call using API.   
$ch \= curl\_init();   
curl\_setopt($ch, CURLOPT\_URL, $url);   
curl\_setopt($ch, CURLOPT\_POST, 1);   
curl\_setopt($ch, CURLOPT\_POSTFIELDS,$args);   
curl\_setopt($ch, CURLOPT\_RETURNTRANSFER, 1); 

// Response  
$response \= curl\_exec($ch);   
$status\_code \= curl\_getinfo($ch, CURLINFO\_HTTP\_CODE);   
curl\_close($ch);   
?\>

Response:  
{  
  "counters": \[  
	{  
  	 "name": "Sandhikharka",  
            "value": "268:sandhikharka-khanepani"  
	},  
	{  
  	"name": "itahari",  
  	"value": "3:itahari-khanepani"  
	}  \],  
  "status": true  
}

Khanepani Details 

**URL : [{{base_url}}](https://services.khalti.com/api/servicegroup/details/worldlink/)/api/servicegroup/details/khanepani/**

Service Params  
**{**  
	**‘month\_id’ : \< number\_select from 1 to 12 inclusive \>**  
	**‘customer\_code’ : \< numeric value , eg : 12 \>**  
	**‘counter’ : \< one of the ‘value’ fields from the response above (counter) e.g:**  
    **268:sandhikharka-khanepani\>**  
	**‘token’:\<Provided token\>**  
**}**

Example  
\<?php 

$url \= "{{base_url}}/api/servicegroup/details/khanepani/";   
$args \= http\_build\_query(array(   
		'token' \=\> '\<token-provided\>',  
		‘month\_id’ \=\> ‘ 1 ‘  //For Baisakh,  
		‘customer\_code’ \=\> ‘1235’,   
		‘counter’ \=\> ‘216:khanepani’

)); 

\# Make the call using API.   
$ch \= curl\_init();   
curl\_setopt($ch, CURLOPT\_URL, $url);   
curl\_setopt($ch, CURLOPT\_POST, 1);   
curl\_setopt($ch, CURLOPT\_POSTFIELDS,$args);   
curl\_setopt($ch, CURLOPT\_RETURNTRANSFER, 1); 

// Response   
$response \= curl\_exec($ch);   
$status\_code \= curl\_getinfo($ch, CURLINFO\_HTTP\_CODE);   
curl\_close($ch);   
?\>  
Response  
{  
	‘status’ : true,  
	‘customer\_code’ : ‘1235’,  
	‘customer\_name’ : ‘पुर्ण कुमार’,  
	‘address’ : ‘इटहरी-6, संगीत चौक’,  
	‘mobile\_number’ : ‘9841123456’  
	‘current\_month\_dues’ : ‘3000’,  
	‘current\_month\_discount’ : ‘50’,  
	‘current\_month\_fine’ : ‘0’,  
	‘total\_credit\_sales\_amount’ : ‘100’,   
	‘total\_advance\_amount’ : ‘1000’,  
	‘previous\_dues’ : ‘0’,  
	‘total\_dues’ : ‘2950’  
}

Khanepani Service Charge

**URL:** [{{base_url}}/api/servicegroup/servicecharge/khanepani/](http://uatservices.khalti.com/api/servicegroup/servicecharge/khanepani/)

NOTE : khanepani service charge of Rs. 5 per transaction 

Service Params:  
{  
	"counter":"\<\<Counter Name\>\>",  
	"token":"{{token}}",  
	"amount": \<\<Amount from detail fetch api\>\>  
}

Example:  
curl \--location '{{base_url}}/api/servicegroup/servicecharge/khanepani/' \\  
\--data '{  
	"counter":"67277:test-khanepani",  
	"token":"cPULwOxpW8Ox2rssJZ5H",  
	"amount": 60000  
}'

Response:  
{  
	"amount": 600,  
	"service\_charge": 5,  
	"status": true  
}

Khanepani Payment

**URL : [{{base_url}}](https://services.khalti.com/api/servicegroup/details/worldlink/)/api/servicegroup/commit/khanepani/**

Service Params  
**{**  
	**‘reference’ : \< unique value sent for each request \>**   
	**‘customer\_code’ : \< numeric value , eg: 12 \>,**  
	**‘counter’ : \<one of the ‘value’ fields from the response above (counter), e.g:**   
**268:sandhikharka-khanepani\>**  
	**‘amount’ : 5000**  
**}’**

**NOTE : The amount in payment API is without charge, charge amount will be deducted from the service account.** 


### Response

{  
    "status": true,  
    "state": "Success",  
    "message": "Successfully Completed Transaction",  
    "extra\_data": {},  
    "detail": "Success",  
    "credits\_consumed": 309,  
    "credits\_available": 35456464.966469494,  
    "id": 78897534  
}

**Incase for due amount** 

{  
    "status": true,  
    "detail": {  
   	 "message": "Successful Payment",  
   	 "due\_amount": "1361"  
    },  
    "message": "Successfully Completed Transaction",  
    "id": 181868,  
    "extra\_data": {},  
    "state": "Success",  
    "due\_amount": "1361"
}