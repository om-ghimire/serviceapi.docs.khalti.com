## **Frequently Asked Questions**

**1)What is this token and which token should we use?**   
	It is a unique secret key that you have to pass along with your request that helps us identify the source of the request.It can be generated from the portal that is provided to you. You can generate two types of token. For testing purpose,you need to generate test token; which is prefixed with TEST and looks something like: TEST:O7QxjFcdueNzAh9aBOsD and for live purpose, generate LIVE token which looks something like : tqZbd7v9ei3iDczA3osT. 

**2\) Why am I getting  the response ‘Problem using the service’ ?**  
	It is required that you first request our support team for addition of service. Unless a service is added to your account, you won’t be able to use that service despite fulfilling all the requirements of a legitimate request.

**3\) Why am I getting ‘token\_not\_found’ ?**  
	It is because the token sent from your end is not consistent with the token you have generated in your portal. Make sure you send the same token that you have generated.

**4\) Why am I getting ‘TEST API not available for this service’ ?**  
	There are few services like Movie, flight for which, currently we don’t have a test environment set up. You can use live credential for testing these services. However, be careful while calling the payment API since it issues the tickets for real. Also, make sure you book flights/hotels with dates far ahead of the current date to prevent booking congestion in real time. 

**5\) Why is it that the status of my transaction is in ‘Processing’ state for so long ?**  
	It could be because of the long processing time taken from the service provider. If the status doesn’t change for a long time, you can try refreshing the transaction manually from the portal given to you. If however the issue still persists, you can call our support for details.

**6\) How do I add balance to my Khalti Service account ?**   
	You can add Khalti Service balance by transferring it from your Khalti account. For this, go to the Credit section in your dashboard and select a subsection under it namely ‘Add Request’. Input the amount of credit to be added under the field Credit and you should see a button ‘Load Directly from khalti’ pop up at the bottom. Click it, put the OTP and transaction PIN and you should be done.

**7\) How to generate the UAT token ?** 

[**Link - Steps for staging(TEST) service account Login and Token Setup**](https://app.tango.us/app/workflow/Steps-for-staging-TEST--service-account-Login-and-Token-Setup-928be4ac17e94caeb37d02c7e576cf4d)



**8\) What are the test credentials ?** 

[**LINK : TEST  CREDENTIALS**](https://docs.google.com/spreadsheets/d/1-6E-\_CJsWFP5VqHmTiWt0FsX2Ft4DRXziAB\_iSM9Wpc/edit\#gid=0)

## **Error Codes**
# Error Codes and Messages

| Error Code | Message                                      |
|------------|----------------------------------------------|
| 1001       | Token not provided                          |
| 1002       | Invalid token                                |
| 1003       | Deleted token is provided                   |
| 1004       | Inactive token is provided                  |
| 1005       | Account associated with token is deleted     |
| 1006       | Account associated with the token is inactive |
| 1007       | Account has expired                         |
| 1008       | Problem using the service                   |
| 1009       | Account doesn't have the permission          |
| 1010       | Validation error                             |
| 1011       | Validation error                             |
| 1012       | Reference id not provided                   |
| 1013       | Request with duplicate reference id obtained|
| 1014       | Parse error                                  |
| 1015       | Parse error                                  |
| 1016       | Insufficient user credits                   |
| 1017       | Server error                                 |
| 1018       | Error while using service                   |
| 1019       | Service in maintenance mode                 |
| 1020       | ERC for the amount could not be obtained     |
| 1021       | Error from Provider                          |
| 4000       | Can’t fulfill request                        |

***Response from api***


### ***How the Error Code and Message Will be Shown***

If your API responds with an error code, it will be accompanied by a message that provides more context about the issue. Here’s how it could be presented:

<pre><code class="json">
{
    "error_code": "1002",
    "message": "Invalid token"
}
</code></pre>
