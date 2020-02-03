# Title
Loading of Untrusted Resources in IFrame

# Risk
Low

# Description

The [TKTK application name] application allows user-supplied URIs to be loaded in IFrames. An attacker can leverage the finding to [TKTK run malicious JavaScript, display fake login forms to steal user credentials].
 
The use of IFrames allow resources to appear inline with the page being loaded. When the `src` attribute of IFrames can be attacker controlled, malicious resources may be displayed to targeted user. For instance, attackers may display fake-login forms to capture their credentials. As IFrames appear inline with trusted content, users are likely to trust malicious content as being part of the web page they are viewing. Additionally, IFrame `src` attributes can include data URIs or JavaScript, which can allow arbitrary JavaScript script to execute.

Following is a screenshot showing the web page https://example.com being embedded into the page [TKTK url goes here].


Following is a HTTP request which contains a user controllable [TKTK query parameter] named [TKTK iframeSrc] for specifying the URI to load in an IFrame.

~~~
[TKTK place request here]
~~~

Following is the HTTP Response which contains an IFrame loading the resource specified by the URL. The response has been modified for brevity.
~~~
[TKTK place request here

HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8
Connection: close
Content-Length: 1000

...
<iframe src="https://example.com">
...
]
~~~



Following is code from the [TKTK application] application. On line [TKTK 31] , user controlled input referenced by the variable [TKTK variable name] is set as the IFrame src attribute.

From [TKTK  URL , the method *SomeController.displayPosts()* defined in *filePath* , the function *displayPosts()* defined in *filePath*, etc]:
~~~
[ TKTK Place code snippet here with numbered lines. Ex:

  313 document.getElemebtById(iframe).src=userInput;
]

~~~




# Proof of Concept

[TKTK Explain Reproduction Steps. Paste request/responses, or explain actions taken through website to exploit,etc.]


# Recommendations

Restrict URIs which can be displayed in IFrames through the use of input validation and white-listing acceptable URIs. Use Content-Security policies to mitigate browsers from loading untrusted resources.

# References

"OWASP Top10-2017 A1-Injection"  - https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A1-Injection
"CWE-1021: Improper Restriction of Rendered UI Layers or Frames  - https://cwe.mitre.org/data/definitions/1021.html
"Content Security Policy" - https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP
