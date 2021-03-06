---

title: API Configurations - disableThirdPartyCookies
description: disableThirdPartyCookies configurations for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Configurations - disableThirdPartyCookies
SEO description: disableThirdPartyCookies configurations for the Adobe Experience Cloud ID Service API
author: giurgiu
doc type: tech doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: ID Service API
guide subtopic 1: ID Service API Configurations
guide subtopic 2: n/a

---

# disableThirdPartyCookies

An optional, Boolean flag that prevents the Experience Cloud ID service from returning the third-party, demdex.net cookie.

[!NOTE]
This configuration was `idSyncDisable3rdPartySyncing` and renamed to `disableThirdPartyCookies` in the January 18, 2018 release of v3.0.

 ## Syntax 
 `disableThirdPartyCookies: true|false` \(default is `false`.\) For `VisitorAPI.js` v1.5.3, or greater.

When `disableThirdPartyCookies: true`, the ID service does not return the third-party, demdex.net cookie \(see [../ID%20service%20production/src/mcvid\_cookies.html\#](../ID%20service%20production/src/mcvid_cookies.html#) \). If a site visitor already has this cookie in their browser, the ID service won't use it to create a new Experience Cloud ID \(MID\) or return an existing ID. Instead, the ID service creates a new, random MID in the first-party cookie. Once enabled, you can collect data with the ID service and share it across different Experience Cloud solutions.

## Code Sample 

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   trackingServer: "Insert tracking server here here",  //Same as s.trackingServer
   trackingServerSecure: "Insert secure tracking server here",  //Same as s.trackingServerSecure

   //For CNAME support only. Exclude these variables if you're not using CNAME
   marketingCloudServer: "Insert tracking server here",
   marketingCloudServerSecure: "Insert secure tracking server here",

   //Function variable
   disableThirdPartyCookies: true
});
```

**Parent topic:** [Configurations](mcvid-function-vars.html)

