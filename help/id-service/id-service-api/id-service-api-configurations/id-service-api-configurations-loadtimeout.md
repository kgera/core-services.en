---

title: API Configurations - loadTimeout
description: loadTimeout configurations for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Configurations - loadTimeout
SEO description: loadTimeout configurations for the Adobe Experience Cloud ID Service API
author: giurgiu
doc type: technical doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: ID Service API
guide subtopic 1: ID Service API Configurations
guide subtopic 2:

---

# loadTimeout

Sets a timeout interval in milliseconds. Used to tell other solutions \(e.g., Analytics, Audience Manager, Target, etc.\) how long to wait for a response from the ID service.

## Syntax
`loadTimeout: interval in milliseconds` 

The default value is 30,000 milliseconds \(30 seconds\). We strongly recommend that you *do not* change the default value.

[!NOTE]
Calls to the ID service are asynchronous in relation to other, non-Adobe code on the page. As a result, increasing or decreasing the timeout interval does not change the rate at which your page renders content. 
However, long timeout intervals may affect page load times as measured by common network monitoring tools, but rendering time is unaffected.
[!END]

## Code Sample

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   trackingServer: "Insert tracking server here here",  //Same as s.trackingServer
   trackingServerSecure: "Insert secure tracking server here",  //Same as s.trackingServerSecure

   //For CNAME support only. Exclude these variables if you're not using CNAME
   marketingCloudServer: "Insert tracking server here",
   marketingCloudServerSecure: "Insert secure tracking server here",

   //Function variable. Example sets the timeout to 10,000 milliseconds (10 seconds).
   loadTimeout:10000
});
```

**Parent topic:** [Configurations](mcvid-function-vars.html)
