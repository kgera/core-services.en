---

title: Content Security Policies and the Experience Cloud ID Service
description: 
SEO title: Content Security Policies and the Adobe Experience Cloud ID Service
SEO description: 
author: gipaul
doc type: technical doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: Reference
guide subtopic 1:
guide subtopic 2:

---

# Content Security Policies and the Experience Cloud ID Service

A Content Security Policy (CSP) is an HTTP header and security feature that gives browsers control over what type of resources are loaded on a Web page. Review this section if you use the ID service and have strict CSPs that use whitelists to accept resources from trusted domains. You will need to add the Adobe domains listed here to your CSP whitelists.

## CSP Review
CSPs use the HTTP header Content-Security-Policy to control the type of resources a browsers accept or load on a page. Applying a CSP can help you prevent:

+ JavaScript files from loading if the source is unknown or not included in a whitelist.
+ Cross-site scripting (XXS) attacks.
+ Data injection attacks.
+ Site defacement attacks.
+ Malware distribution.

The use of CSPs are common and well-understood. It is not the purpose of this documentation to explain CSPs in detail (see the related information links below for more information). What is important is that you understand what Adobe domain names you should add to a CSP if you use these and have tight security policies. Adding these domains will let visitor browsers that access your site to make those important calls for Experience Cloud resources that you use and depend on.

## Experience Cloud Domains for Whitelisting
Add these domain names or URLs to your CSP for each list Experience Cloud solution or service that you use.

| Solution or Service         | Description                                                                                                                                                         |
| :-------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| AppMeasurement              | Modify your CSP to include the following: `\*.2o7.net` and `\ *.omtrdc.net`                                                                                         |
| Target                      | Modify your CSP to include `\*.tt.omtrdc.net`                                                                                                                       |
| Experience Cloud ID Service | Modify your CSP to include `\*.demdex.net`. Calls to the `demdex.net` domain are used to generate the Cookies and the Experience Cloud ID Service and for ID syncs. |

[!MORE]
+ [Understanding Calls to the Demdex Domain](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html)
Useful external reference materials
+ [Content Security Policy Reference](https://content-security-policy.com/)
+ [MDN: Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/CSP)
+ [Wikipedia: Content Security Policy](https://en.wikipedia.org/wiki/Content_Security_Policy)
[!END]
