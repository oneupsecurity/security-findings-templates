# Title
Secrets Generated by Non-Cryptographically Secure Pseudorandom Number Generator

# Risk
High

# Description

The [TKTK application name] application generates [TKTK credential, cryptographic keys] using a Non-Cryptographically Secure Pseudorandom Number Generator. Attackers may exploit the finding to [TKTK predict fucture or past secret values].

Cryptographically Secure Pseudorandom Number Generators (CSPRNG) generates values in which determine previous or future values is not feasible. Pseurandom Number Generators (PRNG) don't exhibit this property, as the output generated by a Non-CSRPNGs may be used to recover internal state of the generator, which can allow for determine past and present values. Non-CSRPNGs may also exhibit biases in their output.


The [TKTK application name] application uses [TKTK Math.random()] to generate [TKTK account recovery tokens, cryptographic keys used to secure chat communications]. [TKTK Math.random()] is not a CSRPNG, meaning attackers may be able to determine the generated value. 

The following code is from the [TKTK application name] application. On line [TKTK 10] [TKTK Math.random()] is used to generate [TKTK a cryptographic key for securing chat communications].

~~~
[TKTK Place code here] 
~~~


# Proof of Concept

[TKTK Explain Reproduction Steps. Paste request/responses, or explain actions taken through website to exploit,etc.]


# Recommendations

Use a Cryptographically Secure Random Number Generator when generating secret values, such as authentication tokens and cryptographis keys. Additionally, ensure the Cryptographically Secure Random Number Generator is seeded with a cryptographically secure (pseudo)random number. [TKTK Rotate secret material generated by the Non-CSRPNG, with material generated by a CSRPNG.]


# References
"OWASP Top 10 2017 A3-Sensitive Data Exposure" - https://owasp.org/www-project-top-ten/OWASP_Top_Ten_2017/Top_10-2017_A3-Sensitive_Data_Exposure.html
"CWE-338: Use of Cryptographically Weak Pseudo-Random Number Generator (PRNG)" - https://cwe.mitre.org/data/definitions/338.html
