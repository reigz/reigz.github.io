## Vulnerability Details

**Credits**: Reigz Macolor (https://github.com/reigz/)<br/>
**Tested On**: Microweber 2.0.10 and 2.0.9.<br/>
**Affected Version**: Microweber 2.0.10  and earlier.<br/>
**Fixed on Version**: Microweber 2.0.11 - https://github.com/microweber/microweber/releases/tag/v2.0.11<br/>
**Fix commit**: https://github.com/microweber/microweber/commit/af61a820194ea1ce2fff98f22262ea3d642920bb 

**Affected Site Page**: /contact<br/>
**Affected Endpoint**: /api/post_form<br/>
CWE-799: Improper Control of Interaction Frequency
## **Details:**
Able to bypass Captcha by bruteforcing, the Microweber CMS doesn't seem to have any brute force protection.

As proof below, where BRUTEFORCEHERE is the parameter we want to brute force:
~~~http
POST /api/post_form HTTP/1.1
...
_token=[REDACTED]&for_id=module-layouts-5--3-contact-form&for=module&your-name=&e-mail-address=&phone=&company=&message=&captcha=[BRUTEFORCEHERE]&module_name=contact_form
~~~

**Vulnerability Impact:**
1. Able to repeat requests, causing spam on contact form.

## **Timeline**

**Feburary 7, 2024** - Reported to Microweber Admin / Developer.<br/>
**Feburary 7, 2024** - Developer confirmed issue is valid for CVE and provided fix.<br/>
**Feburary 10, 2024** - Asked permission to publicly disclose vulnerability to the Developer.<br/>
**Feburary 10, 2024** - Developer agreed for public disclosure.
