# Title
Persistent Cross-Site Scripting

# Risk
High

# Description

The [TKTK application name] application does not encode user controlled input before  [TKTK injecting the content into HTML ]. An attacker can exploit the finding to perform Cross-Site Scripting and [TKTK steal money , escalate privileges , steal users credentials ].


Persistent Cross-Site Scripting (XSS) occurs when user input gets stored on a server and can be evaluated as a client-side browser script. As the script is evaluated under the current user's session who is executing the script, arbitrary actions can be performed on the site as the user. An attacker can therefore [TKTK create a script which grants themselves administrative privileges, when the script is executed by an Administrator]. Additionally, XSS can be used to modify the websites DOM. This can be used to display fake login forms to steal user credentials.

In the [TKTK application name] application, [TKTK Explain what was vulnerable and why. If XSS filtering was used to by the application, explain how it was bypassed.]

Following is code from the [TKTK application] application. On line [TKTK 31] , user controlled input [TKTK variable name] is not encoded for output, allowing [TKTK | HTML to be inserted into the page | a JavaScript string to be terminated early] . This allows arbitrary [TKTK  Javascript ] to be injected into the page.

From [TKTK  URL , the method *SomeController.displayPosts()* defined in *filePath* , the function *displayPosts()* defined in *filePath*, etc]:
~~~
[ TKTK Place code snippet here with numbered lines. Ex:

  313 response.Write("<body>" + userInput + "</body>");
]

~~~

# Proof of Concept

[TKTK Explain Reproduction Steps. Paste request/responses, or explain actions taken through website to exploit,etc.]


# Recommendations

Encode output for the context it is being inserted into to prevent unintended interpretation. For HTML, use of a template engine is highly recommended, as many edge cases after to be considered. Ensure libraries used for encoding have been vetted for security issues. Ensure HTTP response include a `Content-Type` header which represnets the data being returned. Use Content Security Policy (CSP) to mitigate XSS attacks, such as disabling JavaScript's use of *eval()* and processing of inline scripts.

# References

"OWASP Top 10-2017 A7-Cross-Site Scripting (XSS)" - https://www.owasp.org/index.php/Top_10-2017_A7-Cross-Site_Scripting_(XSS)  
"Content Security Policy" - https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP
