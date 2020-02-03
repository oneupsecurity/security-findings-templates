# Title

Permissive Deserialization of Unsafe Types

# Risk
[TKTK Modify risk based on context.] High

# Description

The [TKTK application name] uses [TKTK BinaryFormatter for deserialization], which by default does not restrict types which can be deserialized. Types which were not designed to be deserialized from untrusted data streams can be leveraged to gain Remote Code Execution.

The [TKTK BinaryFormatter] serializer uses types within serialized data streams to determine to instantiated. By default the deserializer allows core .NET types to be deserialized. Multiple .NET core types may perform side-effects when instantiated, and were not designed to be deserialized from untrusted data sources. For instance, the [TKTK type `MulticastDelegate`] can be leveraged to execute arbitrary commands.

Following is code from the [TKTK application] application. On line [TKTK 31] , user controlled input is passed to the method [TKTK deserializer.Deserialize()]. As the deserilaizer does not restrict types which can be deserialized, types such as [TKTK ObjectDataProvider] can be leveraged to [TKTK perform arbitrary remote code execution] .

From [TKTK  URL , the method *SomeController.displayPosts()* defined in *filePath* , the function *displayPosts()* defined in *filePath*, etc]:
~~~
[ TKTK Place code snippet here with numbered lines. Ex:

  313 document.getElemebtById(iframe).src=userInput;
]

~~~


# Proof of Concept


Following is a HTTP request to the endpoint [TKTK https://example.com] . The [TKTK POST body] contains user-supplied serialized data.

~~~
[TKTK place request here]
~~~

Following is the HTTP Response showing the request was accepted and processed. 

~~~
[TKTK place request here

HTTP/1.1 200 OK
Content-Type: text/html; charset=utf-8
Connection: close
Content-Length: 1000

...
someBinaryData
...
]
~~~


When deserialized, the process [TKTK parent.exe] spawns a child process [TKTKT calc.exe], as shown by the following image.



# Recommendations

Configure deserilaizer to restrict types to only expected types. Do not allow security-sensitive properties to be set by untrusted data sources, without proper authorization and input validation checks. [TKTK For .NET: See Microsoft's article on Security Considerations for Data for more details.]

# References

"OWASP Top10-2017 A1-Injection"  - https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A1-Injection
"CWE-1021: Improper Restriction of Rendered UI Layers or Frames  - https://cwe.mitre.org/data/definitions/1021.html
"Content Security Policy" - https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP
"Friday	the	13th: JSON Attacks" - https://www.blackhat.com/docs/us-17/thursday/us-17-Munoz-Friday-The-13th-Json-Attacks.pdf
[ TKTK For .NET
"Windows Communication Foundation, Serialization and Deserialization" - https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/serialization-and-deserialization   
"Windows Communication Foundation, Security Considerations for Data , Preventing Unintended Types from Being Loaded" https://docs.microsoft.com/en-us/dotnet/framework/wcf/feature-details/serialization-and-deserialization
]
