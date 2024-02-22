## Vulnerability Details


**Credits**: Reigz Macolor (https://github.com/reigz/)<br/>
**Tested On**: Microweber 2.0.10 and 2.0.9.<br/>
**Affected Version**: Microweber 2.0.10  and earlier.<br/>
**Fixed on Version**: Microweber 2.0.11 - https://github.com/microweber/microweber/releases/tag/v2.0.11<br/>
**Fix commit**: https://github.com/microweber/microweber/commit/5ce8ba440e193942e17dc1d7e5bdd01bb80123e6

**Affected Site Page**: /shop<br/>
**Affected Endpoint**: /api/update_cart<br/>
CWE-200: Exposure of Sensitive Information to an Unauthorized Actor

## **Details:**
Upon trying to checkout on your shop page on demo:

~~~http
POST /api/update_cart HTTP/1.1
...
content_id=<change_number_here>
~~~

## **Vulnerability Impact:**
As an attacker, can do the following:
1. See all page content and retrieve them as "items" in the cart.
2. In case an owner of a site decides to place items and do not display them yet in the site but add them in the backend, there is a possibility that I am able to retrieve it.
3. Possibility to access pages not normally traversable in the UI.

## **Timeline**

**Feburary 7, 2024** - Reported to Microweber Admin / Developer.<br/>
**Feburary 7, 2024** - Developer confirmed issue is valid for CVE and provided fix.<br/>
**Feburary 10, 2024** - Asked permission to publicly disclose vulnerability to the Developer.<br/>
**Feburary 10, 2024** - Developer agreed for public disclosure.
