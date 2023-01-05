# Does SharePoint handle search for things not in SharePoint?

Nope.

> The answer to what you're asking to do is simply not possible. The reason why you can't index external content is because Microsoft doesn't provide access to the Crawl configuration. This area of the SharePoint Online implementation is a black box managed by Microsoft and Microsoft alone. It's not hidden, obfuscated or disabled "by default" - it simply is not available. As to why that is the case, remember that SPO is a (complex) multi-tenant implementation of SharePoint, where behind the scenes multiple domains are shared within single deployments. Add to that the fact that Search crawl is one of the most variable and highly impactful processes you can possibly configure within a farm. Together, it's understandable why the option is not available (at this point in time).


* How can I get external content crawled into SharePoint online index  
  <https://sharepoint.stackexchange.com/questions/88558/how-can-i-get-external-content-crawled-into-sharepoint-online-index>
* Make sure content can be found - SharePoint in Microsoft 365 \| Microsoft Learn  
  <https://learn.microsoft.com/en-us/sharepoint/make-sure-content-can-be-found>
* Overview of search in SharePoint - SharePoint in Microsoft 365 \| Microsoft Learn  
  <https://learn.microsoft.com/en-us/sharepoint/overview-of-search>

