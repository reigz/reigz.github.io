Credits: Reigz Macolor (https://github.com/reigz/)

Tested On: Microweber 2.0.10 and below

Affected Version: Microweber 2.0.10 - https://github.com/microweber/microweber/releases/tag/v2.0.10

Affected Site Page: https://demo.microweber.org/demo/shop

Fixed on Version: Microweber 2.0.10 - https://github.com/microweber/microweber/releases/tag/v2.0.11


**Details:**
Upon trying to checkout on your shop page on demo:

~~~http
POST /demo/api/update_cart HTTP/1.1
Host: demo.microweber.org
...
content_id=<change_number_here>
~~~

**Vulnerability Impact:**
As an attacker, I am able to do two things:
1. See all page content and retrieve them as "items" in the cart.
2. In case an owner of a site decides to place items and do not display them yet in the site but add them in the backend, there is a possibility that I am able to retrieve it.
3. Possibility to access pages not normally traversable in the UI.
