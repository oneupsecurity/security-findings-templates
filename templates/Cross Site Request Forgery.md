# Title
Cross-Site Request Forgery

# Risk
Medium

# Description

The [TKTK application] does not verify the authenticity of requests. Attackers can force users to send requests to [TKTK add new user accounts, login to an account].

Cross-Site Request Forgery occurs when attackers can force targets users to perform unintended actions against an application. Attackers may force users to perform unintended actions such as by leveraging iframes, AJAX requests, form posts, or tricking users into clicking a maliciously crafted link.
  
The following code is from the [TKTK application name] application. Note the request's authenticity is not verified. For instance, Anti Cross-Site Request Forgery Tokens are not verified in the code. This allows [TKTK].

From [TKTK  URL , the method *SomeController.addUser()* defined in *filePath* , the function *addUsers()* defined in *filePath*, etc]:
~~~
[ TKTK Place code snippet here with numbered lines. Ex:

  313 function addUserEndpointHandler(postData) {
  314    users.addUser(postData);
  315 }
]

~~~

# Proof of Concept

The following request was sent to the endpoint [TKTK https://example.com]. Note the request does not contain cookies or post data which can be used to verify the request was intentionally sent.

The following HTTP response is received.

~~~
[TKTK place code snippet here] 
~~~

The following HTML page can be used to auto-submit a log in form request when viewed.

~~~
[TKTK PLACE HTML AND JAVASCRIPT HERE WHICH WILL AUTO SUBMIT HTTP REQUEST WHEN VIEWED]
~~~




# Recommendations

Require users to send an authentication token which is unique to each user. Ensure the authentication token is not automatically sent when a request is originated from another origin. Ensure the authentication token is generated using a cryptographically secure random number generator, and has a high amount of entropy, such as 128 bits. 

[TKTK add for .net apps: See Microsoft's article on preventing Cross-Site Request Forgery attacks in ASP.NET core.]

Setting the `SameSite` flag on security sensitive cookies to `strict` or `lax` is recommended to mitigate cookies being sent from untrusted origins is recommended.

# References


"A2-Broken Authentication" - https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A2-Broken_Authentication
"CWE-352: Cross-Site Request Forgery (CSRF)" - https://cwe.mitre.org/data/definitions/352.html
[TKTK add for .net applications  "Prevent Cross-Site Request Forgery (XSRF/CSRF) attacks in ASP.NET Core]" - https://docs.microsoft.com/en-us/aspnet/core/security/anti-request-forgery?view=aspnetcore-3.1]
