# Download Ticket API Documentation

## Overview

This document describes the API for downloading a bus ticket. The API allows users to retrieve a ticket in a specified format using their booking details.

## API Endpoint

**Request URL:** `{{base_url}}/api/servicegroup/downloadticket/bus/`  
**Request Method:** POST

### Request Parameters
<pre><code class="json">
{
    "token": "{{token}}",
    "reference": "{{$guid}}",
    "bus_id": "{{bus_id}}",
    "session_id": "{{session_id}}"
}
</code></pre>

### API Response

#### Success Response

<pre><code class="json">
{
    "status": true,
    "data": "JVBERi0xLjUKJbXtrvsKNCAwIG9iago8PCAvTGVuZ3RoIDUgMCBSCiAgIC9GaWx0ZXIgL0ZsYXRl\nRGVjb2RlCj4+CnN0cmVhbQp4nN1V32/bNhB+119xj9QA0UeKFMUgCFbHKYIM8dpaRR/cPTCOHHuJ\nrUSWt+a/31E/bNkuhuWlwArDsnnkfXff8e6TAKRPJOiRKgGzVfASfISXIJFcahDacqMkKIPcGAP0\n1FDm8AXWAdae5QMMHMLDpvNIkCsrYQU6jjlKs7M87S1WcFtbWp/denEUt4fSWvoosrV0KN36FGX+\nS59UG+6nIiW15orI/HdSUidcUsh9Op1ln45MDTe1pfXZrRdHcfsojaWPkraWDqVbn6IckmrD/VSk\n4lgRwBs4eYeDZFrDPpc4IY77VHbLxWHIQwSUBwimMXQI7fIE4ZBKE+j/TeU402EWpP5crYv1v3bw\njOVSoI1TyFbBYB5hhCAgmwdT9j4UKSuLFZzBb65arNz6fhv+kd0EXloFT1CJxEB2H7BhUTzm93D3\nCmH2p9+2XEuMk3rzslhXblbBKK/c8mnjT1xlvXoTlRg1GN9tVGvVFfslMG2+tV2nwrZJ24Rjgn5N\nyt4QhME3A6Mi+Pg29pJkRyY6kcfsWbacPeYVeGbL9QMQCZ/4YPLs1nB+DoN3s2rrnrL8WwXn83w+\nR0wS+toLuLiA4eiyQRMN2jkiigtP/PbyMEy5ctWyxZ5HorN70iTFcWyEr+GUXZa5q6jE70JhWAUS\npYxQRCKuL6QPKSVPpZapgijmGpWJdQORhUJoVtBtfgilYcXjwpWuc99FZtDmsgOMeoiSa2O1qhHZ\nKH92ZbWl68qWq/yYAgMUZ4jw4fYEccpuim25zl/hmn6bFP6lsA53RZ1Sev54Xccf49KjNGUaTuo9\nZZPFcl69hcUh5o9mNGXj5cOiOmWCJEr+46851omOVdM4w+0GfPMge33OwyiRVrDfn/PSVUVzeVKR\nZ6rQ0njtPMZFGKk0lqwboRE1cG0S1IpGstL9lT811uMmjPaIkSApSWxqG+Sb7equgOulm+Ut/Ji6\n8Alul7OyuNtuaijSTGGUEUmXT"
}
</code></pre>

## Conclusion

This API allows clients to download their bus tickets after a successful booking. Ensure that all provided parameters are valid for successful retrieval of the ticket.
