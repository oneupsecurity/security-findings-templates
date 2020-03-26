
# Title

Server-Side Request Forgery (SSRF)

# Risk
Medium

# Description

The [TKTK application] allows users to specify the destination of HTTP requests. Attackers can leverage the finding to [TKTK send requests to internal systems]. 

Server-Side Request Forgery (SSRF) attacks occur when user input causes server applications to send HTTP requests to unintended destinations. Attackers may use SSRF attacks to bypass firewalls in order to communicate with internal systems in which the server application is hosted on. [TKTK Attackers may also attempt to steal sensitive information in requests, such as authentication credentials, by forcing the application to send requests to attacked controlled server.]

Following is [TKTK application name] application code. On line [TKTK 10] a request is sent to the host address specified by the user-controlled [TKTK query parameter named TKTK]. As the user-controlled data is not validated, HTTP requests can be sent to arbitrary destinations.

From [TKTK filepath, the method *SomeController.sendRequest()* defined in *filePath* , the function *addUsers()* defined in *filePath*, etc]:
~~~
[ TKTK Place code snippet here with numbered lines. Ex:

  313 sendHTTPGetRequest(url);
]

~~~

# Proof of Concept

The following request was sent to the endpoint [TKTK https://example.com]. Note how the [TKTK query parameter urlParmName] is set to [TKTK http://example.com/desUrl]. 

~~~
[TKTK place http request here]
~~~

[TKTK The following HTTP request was then received by the host example.com

OR

The following HTTP Response was returned by https://example.com . Note how the returned HTTP response includes data from http://example.com/destinationAddress 

]

~~~
[TKTK place request/response here]
~~~



# Recommendations

Add input validation to restrict request from being sent to unintended hosts. When possible, use a white-list approach to limit acceptable values. [TKTK if possible, do not rely upon user supplied data to determine the destination of requests.]  

# References

"OWASP Top 10 2017 A1-Injection" - https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A1-Injection
"CWE-918: Server-Side Request Forgery (SSRF)"- https://cwe.mitre.org/data/definitions/918.html
