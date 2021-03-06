---

title: API Methods - appendSupplementalDataIDTo
description: appendSupplementalDataIDTo helper method for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Methods - appendSupplementalDataIDTo
seo-description: appendSupplementalDataIDTo helper method for the Adobe Experience Cloud ID Service API
short-title: free text
doc-type: article
author: name
index: yes
translate: yes
version:
private-feature-pack:
beta:
redirect:

---

# appendSupplementalDataIDTo

This helper method lets you append the Supplemental Data ID `SDID` as a query string parameter to a redirect URL. 

This is useful when using A4T and you need to persist the `SDID` from one page to another and stitch those separate visits together. To use this function, you must have implemented the ID service with the same Organization ID on the source and destination domains.
  

## Syntax
`appendSupplementalDataIDTo(URL,SDID)` 

## Code Sample

```javascript {.line-numbers}
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   ...
});

//Call helper method to append SDID to the Page B URL from Page A
var pageB = "www.domain.com/pageB";
var pageBWithSdid = visitor.appendSupplementalDataIDTo(pageB, "67987653465787219");
```

## Sample Output

As shown below, the URL redirect contains the visitor's `SDID`, your Organization ID, and a UNIX timestamp in the call to the receiving page.

`www.domain.com/pageB?adobe_mc_sdid=SDID=123|MCORGID=123456789@AdobeOrg|TS=1498569322` 
  

## Changing the SDID Timeout with sdidParamExpiry

The [sdidParamExpiry](mcvid-sdidparamexpiry.html#) configuration lets you change the default `SDID` expiration interval when passing that ID from one page to another using the `appendSupplementalDataIDTo` helper function. 

[!NOTE]
By default, the ID service code on the receiving page has 30 seconds to get the `SDID` from the URL sent by the referring page. If the ID service code on the receiving page can't retrieve the `SDID` in less than 30 seconds it requests a new `SDID`. This functionality is mainly for A4T customers who need to pass the `SDID` from one page to another and want control over this timeout interval.
[!END]

If you need to change the default 'SDID' timeout, add `sdidParamExpiry` to the `Visitor.getInstance` function with the following syntax:

## Syntax

`sdidParamExpiry: time in seconds` 

## Code Sample

When configured your ID service code could look similar to this sample. This sample sets the SDID timeout to 15 seconds.

```javascript {.line-numbers}
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   ...
   //Change the default SDID timeout to 15 seconds
   sdidParamExpiry: 15
});

//Call helper method to append SDID to the Page B URL from Page A
var pageB = "www.domain.com/pageB";
var pageBWithSdid = visitor.appendSupplementalDataIDTo(pageB, "67987653465787219");

```
