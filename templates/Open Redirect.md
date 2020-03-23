# Title
Open Redirect

# Risk
Medium

# Description

The [TKTK application name] application allows user-controlled data to specify arbitrary URIs for redirects. Attackers may leverage in phishing attacks to [TKTKT steal credentials].


Open redirects occur when user-controlled data, such as a URI, can be used redirect users to load an untrusted resource. As the endpoint containing the redirect finding is hosted on the domain [TKTK exmaple.com], users are more likely to trust the landing page of the re-direct as legitimate.

In the [TKTK application name] application, the endpoint [TKTK https://example.com/redirect?url=] is used to re-redirect users to [TKTK external websites, web pages beloning to the application]. As the application does not restirct which resources which are redirectable to, attackers may craft malicious links to malicious web pages.

Following is code from the [TKTK application] application. On line [TKTK 31] , user controlled is not validated before being used to redirect users to the specified resource.

From [TKTK  URL , the method *SomeController.redirectUser()* defined in *filePath* , the function *redirectUser()* defined in *filePath*, etc]:
~~~
[ TKTK Place code snippet here with numbered lines. Ex:

  313 response.redirect(url);
]

~~~

The following HTTP request and response demonstrates the finding. Note how the parameter [TKTK parameter name] is used by the application to specify the re-direct.

HTTP Request:

[TKTK place http request] 

HTTP Response:

[TKTK place http response]] 


# Proof of Concept

[TKTK Explain Reproduction Steps. Paste request/responses, or explain actions taken through website to exploit,etc.]


# Recommendations

Restrict user-input to allow redirections to expected resources. For instance, validation can occur against a white-list of acceptable resources.

# References

"OWASP Top 10-2017 A1-Injection" - https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A1-Injection.html
