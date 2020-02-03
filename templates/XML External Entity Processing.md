# Title
[TKTK Data Exfiltration, Remote Code Execution] through XML External Entity Processing (XXE)

# Risk
High

# Description

The [TKTK application name] application processes external entities defined in user-supplied XML. An [TKTK authenticated attacker, attacker with normal privileges] can exploit the finding to [TKTK read arbitrary files from disk, perform Server-Side Request Forgery to reach sensitive endpoints, perform denial of service attacks.]

The XML specification allows Document Type Definitions to define external entities, which refer too external resources. XML parsers which are configured to process external entities often allow resources obtained from URIs to be embedded in the document and sent to remote hosts. Supported URI protocols are dependent on the parser's implementation, but commonly support *file://*,  *http://*, *https://*, and *ftp://*.  This allows for [TKTK Some URI handlers, such as PHP's expect protocol (expect://) allows arbitrary code to be executed.] 

In the [TKTK application name] application, user controlled XML is [TKTKTK processed by the endpoint http://example.com].

The following code from the [TKTK application] application processes XML. On line [TKTK 31] ,the XML processor is instantiated. As the XML processor's default configuration is not overridden, XML entities will be processed if supplied. On line [TKTKT 31] the application processes the XML which is user controllable. This allows attackers to supply malicious XML which [TKTK exfiltrates local files to remote hosts, send GET requests to web services on TKTK's private network].

From [TKTK URL , the method *SomeClass.displayPosts()* defined in *filePath* , the function *displayPosts()* defined in *filePath*, etc]:
~~~
[ TKTK Place code snippet here with numbered lines. Ex:

  300 xmlProcessor = new XmlProcessor();
  ...
  313 xmlProcessor.parse(userXml)
]

~~~

# Proof of Concept

[TKTK Explain Reproduction Steps. Paste request/responses, or explain actions taken through website to exploit,etc.]

The following HTTP request and response demonstrates exploitability of the finding. 

Request:

[TKTK replace me]

Response:

[TKTK Replace me]

# Recommendations

Configure XML parsers to disable processing of Document Type Definitions and entities. If use of external entities or doc type definitions are required, validate and encode user input to prevent Document Type Definitions and entities from being defined and referenced. Refer to OWASP's XML External Entity Prevention Cheat Sheet for securing common XML parsers.


# References

"OWASP Top 10-2017 A4-XML External Entities (XXE)" - https://www.owasp.org/index.php/Top_10-2017_A4-XML_External_Entities_(XXE)
"CWE-611: Improper Restriction of XML External Entity Reference" - https://cwe.mitre.org/data/definitions/611.html
"OWASP https://owasp.org/www-project-cheat-sheets/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html" - https://owasp.org/www-project-cheat-sheets/cheatsheets/XML_External_Entity_Prevention_Cheat_Sheet.html 
