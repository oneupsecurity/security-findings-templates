# Title
Horizontal Privlege Escalation (Direct Object Reference)

# Risk
High

# Description

The [TKTK application name] application does not restrict users from accessing [TKTK data belonging to other users]. 

Horizontal privilege escalation vulnerabilities occur when users can unintentionally access data belonging to other users. By knowing or enumerating [TKTK identifiers, file paths]  of resources, attackers can access the data.

The following code from the [TKTK application name] application handles  [TKTK returning documents to users]. Note on line [TKTK 31] how authorization checks are not in place to prevent users from [TKTK reading documents, writing documents] belonging to other users.

From [TKTK  URL , the method *SomeController.displayPosts()* defined in *filePath* , the function *displayPosts()* defined in *filePath*, etc]:
~~~
[ TKTK Place code snippet here with numbered lines. Ex:

  300 return document.getById(docId)
]

~~~

# Proof of Concept

[TKTK Explain Reproduction Steps. Paste request/responses, or explain actions taken through website to exploit,etc.]


# Recommendations

Add authorization checks to restrict [TKTK user, groups, companies] from accessing [TKTK each other's data]. Solely relying on cryptographically strong identifiers is not recommended, as identifiers may leak through unintended channels such as [TKTK emails , comment systems, screenshots].

# References


"OWASP Top 10-2017 A5-Broken Access Control":https://www.owasp.org/index.php/Top_10-2017_A5-Broken_Access_Control
"CWE-285: Improper Authorization":https://cwe.mitre.org/data/definitions/285.html
