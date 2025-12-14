# ZAP by Checkmarx Scanning Report BookingSystem-Phase3 Kati

ZAP by [Checkmarx](https://checkmarx.com/).


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 0 |
| Medium | 1 |
| Low | 4 |
| Informational | 4 |




## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- |
| Cross-Domain Misconfiguration | Medium | 3 |
| Server Leaks Version Information via "Server" HTTP Response Header Field | Low | 1 |
| Strict-Transport-Security Header Not Set | Low | 17 |
| Timestamp Disclosure - Unix | Low | 18 |
| X-Content-Type-Options Header Missing | Low | 17 |
| Authentication Request Identified | Informational | 3 |
| Re-examine Cache-control Directives | Informational | 18 |
| Retrieved from Cache | Informational | 20 |
| Session Management Response Identified | Informational | 5 |




## Alert Detail



### [ Cross-Domain Misconfiguration ](https://www.zaproxy.org/docs/alerts/10098/)



##### Medium (Medium)

### Description

Web browser data loading may be possible, due to a Cross Origin Resource Sharing (CORS) misconfiguration on the web server.

* URL: https://firefox.settings.services.mozilla.com/v1/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `access-control-allow-origin: *`
  * Other Info: `The CORS misconfiguration on the web server permits cross-domain read requests from arbitrary third party domains, using unauthenticated APIs on this domain. Web browser implementations do not permit arbitrary third parties to read the response from authenticated APIs, however. This reduces the risk somewhat. This misconfiguration could be used by an attacker to access data that is available in an unauthenticated manner, but which uses some other form of security, such as IP address white-listing.`
* URL: https://firefox.settings.services.mozilla.com/v1/buckets/main/collections/mfcdm-origins-list/changeset%3F_expected=1750871406038

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `access-control-allow-origin: *`
  * Other Info: `The CORS misconfiguration on the web server permits cross-domain read requests from arbitrary third party domains, using unauthenticated APIs on this domain. Web browser implementations do not permit arbitrary third parties to read the response from authenticated APIs, however. This reduces the risk somewhat. This misconfiguration could be used by an attacker to access data that is available in an unauthenticated manner, but which uses some other form of security, such as IP address white-listing.`
* URL: https://firefox.settings.services.mozilla.com/v1/buckets/monitor/collections/changes/changeset%3Fcollection=mfcdm-origins-list&bucket=main&_expected=0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `access-control-allow-origin: *`
  * Other Info: `The CORS misconfiguration on the web server permits cross-domain read requests from arbitrary third party domains, using unauthenticated APIs on this domain. Web browser implementations do not permit arbitrary third parties to read the response from authenticated APIs, however. This reduces the risk somewhat. This misconfiguration could be used by an attacker to access data that is available in an unauthenticated manner, but which uses some other form of security, such as IP address white-listing.`


Instances: 3

### Solution

Ensure that sensitive data is not available in an unauthenticated manner (using IP address white-listing, for instance).
Configure the "Access-Control-Allow-Origin" HTTP header to a more restrictive set of domains, or remove all CORS headers entirely, to allow the web browser to enforce the Same Origin Policy (SOP) in a more restrictive manner.

### Reference


* [ https://vulncat.fortify.com/en/detail?category=HTML5&subcategory=Overly%20Permissive%20CORS%20Policy ](https://vulncat.fortify.com/en/detail?category=HTML5&subcategory=Overly%20Permissive%20CORS%20Policy)


#### CWE Id: [ 264 ](https://cwe.mitre.org/data/definitions/264.html)


#### WASC Id: 14

#### Source ID: 3

### [ Server Leaks Version Information via "Server" HTTP Response Header Field ](https://www.zaproxy.org/docs/alerts/10036/)



##### Low (High)

### Description

The web/application server is leaking version information via the "Server" HTTP response header. Access to such information may facilitate attackers identifying other vulnerabilities your web/application server is subject to.

* URL: https://content-signature-2.cdn.mozilla.net/g/chains/202402/remote-settings.content-signature.mozilla.org-2026-01-27-09-17-39.chain

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `AmazonS3`
  * Other Info: ``


Instances: 1

### Solution

Ensure that your web server, application server, load balancer, etc. is configured to suppress the "Server" header or provide generic details.

### Reference


* [ https://httpd.apache.org/docs/current/mod/core.html#servertokens ](https://httpd.apache.org/docs/current/mod/core.html#servertokens)
* [ https://learn.microsoft.com/en-us/previous-versions/msp-n-p/ff648552(v=pandp.10) ](https://learn.microsoft.com/en-us/previous-versions/msp-n-p/ff648552(v=pandp.10))
* [ https://www.troyhunt.com/shhh-dont-let-your-response-headers/ ](https://www.troyhunt.com/shhh-dont-let-your-response-headers/)


#### CWE Id: [ 497 ](https://cwe.mitre.org/data/definitions/497.html)


#### WASC Id: 13

#### Source ID: 3

### [ Strict-Transport-Security Header Not Set ](https://www.zaproxy.org/docs/alerts/10035/)



##### Low (High)

### Description

HTTP Strict Transport Security (HSTS) is a web security policy mechanism whereby a web server declares that complying user agents (such as a web browser) are to interact with it using only secure HTTPS connections (i.e. HTTP layered over TLS/SSL). HSTS is an IETF standards track protocol and is specified in RFC 6797.

* URL: https://content-signature-2.cdn.mozilla.net/g/chains/202402/remote-settings.content-signature.mozilla.org-2026-01-27-09-17-39.chain

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/bundles/startup.json.mozlz4

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/08a8f48e-5b5a-4593-9a91-5dcc5f5e514f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/0a25e3cf-57e3-4a0b-a44d-b7cb3ab73662

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/0e2c24a9-7cd1-466a-a9ac-c3559136642a

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/18b1efba-40d6-48a0-a884-fd91b9b79df7

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/1f8e6b6a-9b58-42de-bba4-1675db62f126

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/4638171c-3218-4bf0-af68-d762778aa7ff

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/4704c49a-9fc7-419f-b0e1-0fbffe584885

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/737afe58-ef5e-44c9-84cf-2bba5203d88e

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/80316f8f-6578-4450-97ef-137ff5d04db0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/c93ceb0e-0ed0-43c4-bc87-c8abeca12ca6

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/d09f9f1a-2a51-487c-985d-9410ea926f05

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/e63ff142-39d8-4126-b426-d031f4ae582f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/f2a3db30-40f1-449b-a0ac-79705bfb2833

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/f6ecb0b5-8e71-4cc5-97a5-09e3d9090efe

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/fcf77341-ee13-47db-bdf4-5cad24a9176f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``


Instances: 17

### Solution

Ensure that your web server, application server, load balancer, etc. is configured to enforce Strict-Transport-Security.

### Reference


* [ https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html ](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html)
* [ https://owasp.org/www-community/Security_Headers ](https://owasp.org/www-community/Security_Headers)
* [ https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security ](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
* [ https://caniuse.com/stricttransportsecurity ](https://caniuse.com/stricttransportsecurity)
* [ https://datatracker.ietf.org/doc/html/rfc6797 ](https://datatracker.ietf.org/doc/html/rfc6797)


#### CWE Id: [ 319 ](https://cwe.mitre.org/data/definitions/319.html)


#### WASC Id: 15

#### Source ID: 3

### [ Timestamp Disclosure - Unix ](https://www.zaproxy.org/docs/alerts/10096/)



##### Low (Low)

### Description

A timestamp was disclosed by the application/web server. - Unix

* URL: https://firefox-settings-attachments.cdn.mozilla.net/bundles/startup.json.mozlz4

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1703946492`
  * Other Info: `1703946492, which evaluates to: 2023-12-30 16:28:12.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/bundles/startup.json.mozlz4

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1773959826`
  * Other Info: `1773959826, which evaluates to: 2026-03-20 00:37:06.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/bundles/startup.json.mozlz4

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1827377968`
  * Other Info: `1827377968, which evaluates to: 2027-11-28 06:59:28.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/08a8f48e-5b5a-4593-9a91-5dcc5f5e514f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/0a25e3cf-57e3-4a0b-a44d-b7cb3ab73662

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/0e2c24a9-7cd1-466a-a9ac-c3559136642a

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/18b1efba-40d6-48a0-a884-fd91b9b79df7

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/1f8e6b6a-9b58-42de-bba4-1675db62f126

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/4638171c-3218-4bf0-af68-d762778aa7ff

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/4704c49a-9fc7-419f-b0e1-0fbffe584885

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/737afe58-ef5e-44c9-84cf-2bba5203d88e

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/80316f8f-6578-4450-97ef-137ff5d04db0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/c93ceb0e-0ed0-43c4-bc87-c8abeca12ca6

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/d09f9f1a-2a51-487c-985d-9410ea926f05

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/e63ff142-39d8-4126-b426-d031f4ae582f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/f2a3db30-40f1-449b-a0ac-79705bfb2833

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/f6ecb0b5-8e71-4cc5-97a5-09e3d9090efe

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/fcf77341-ee13-47db-bdf4-5cad24a9176f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1762909803`
  * Other Info: `1762909803, which evaluates to: 2025-11-12 03:10:03.`


Instances: 18

### Solution

Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.

### Reference


* [ https://cwe.mitre.org/data/definitions/200.html ](https://cwe.mitre.org/data/definitions/200.html)


#### CWE Id: [ 497 ](https://cwe.mitre.org/data/definitions/497.html)


#### WASC Id: 13

#### Source ID: 3

### [ X-Content-Type-Options Header Missing ](https://www.zaproxy.org/docs/alerts/10021/)



##### Low (Medium)

### Description

The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'. This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type. Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.

* URL: https://content-signature-2.cdn.mozilla.net/g/chains/202402/remote-settings.content-signature.mozilla.org-2026-01-27-09-17-39.chain

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/bundles/startup.json.mozlz4

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/08a8f48e-5b5a-4593-9a91-5dcc5f5e514f

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/0a25e3cf-57e3-4a0b-a44d-b7cb3ab73662

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/0e2c24a9-7cd1-466a-a9ac-c3559136642a

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/18b1efba-40d6-48a0-a884-fd91b9b79df7

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/1f8e6b6a-9b58-42de-bba4-1675db62f126

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/4638171c-3218-4bf0-af68-d762778aa7ff

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/4704c49a-9fc7-419f-b0e1-0fbffe584885

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/737afe58-ef5e-44c9-84cf-2bba5203d88e

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/80316f8f-6578-4450-97ef-137ff5d04db0

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/c93ceb0e-0ed0-43c4-bc87-c8abeca12ca6

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/d09f9f1a-2a51-487c-985d-9410ea926f05

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/e63ff142-39d8-4126-b426-d031f4ae582f

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/f2a3db30-40f1-449b-a0ac-79705bfb2833

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/f6ecb0b5-8e71-4cc5-97a5-09e3d9090efe

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/fcf77341-ee13-47db-bdf4-5cad24a9176f

  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`


Instances: 17

### Solution

Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.
If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.

### Reference


* [ https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/compatibility/gg622941(v=vs.85) ](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/compatibility/gg622941(v=vs.85))
* [ https://owasp.org/www-community/Security_Headers ](https://owasp.org/www-community/Security_Headers)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 15

#### Source ID: 3

### [ Authentication Request Identified ](https://www.zaproxy.org/docs/alerts/10111/)



##### Informational (High)

### Description

The given request has been identified as an authentication request. The 'Other Info' field contains a set of key=value lines which identify any relevant fields. If the request is in a context which has an Authentication Method set to "Auto-Detect" then this rule will change the authentication to match the request identified.

* URL: http://localhost:8003/login

  * Method: `POST`
  * Parameter: `username`
  * Attack: ``
  * Evidence: `password`
  * Other Info: `userParam=username
userValue=admin@admin.fi
passwordParam=password
referer=http://localhost:8003/login
csrfToken=csrf_token`
* URL: http://localhost:8003/login

  * Method: `POST`
  * Parameter: `username`
  * Attack: ``
  * Evidence: `password`
  * Other Info: `userParam=username
userValue=foo-bar@example.com
passwordParam=password
referer=http://localhost:8003/login
csrfToken=csrf_token`
* URL: http://localhost:8003/login

  * Method: `POST`
  * Parameter: `username`
  * Attack: ``
  * Evidence: `password`
  * Other Info: `userParam=username
userValue=reserver@reserver.fi
passwordParam=password
referer=http://localhost:8003/login
csrfToken=csrf_token`


Instances: 3

### Solution

This is an informational alert rather than a vulnerability and so there is nothing to fix.

### Reference


* [ https://www.zaproxy.org/docs/desktop/addons/authentication-helper/auth-req-id/ ](https://www.zaproxy.org/docs/desktop/addons/authentication-helper/auth-req-id/)



#### Source ID: 3

### [ Re-examine Cache-control Directives ](https://www.zaproxy.org/docs/alerts/10015/)



##### Informational (Low)

### Description

The cache-control header has not been set properly or is missing, allowing the browser and proxies to cache content. For static assets like css, js, or image files this might be intended, however, the resources should be reviewed to ensure that no sensitive content will be cached.

* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/08a8f48e-5b5a-4593-9a91-5dcc5f5e514f

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/0a25e3cf-57e3-4a0b-a44d-b7cb3ab73662

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/0e2c24a9-7cd1-466a-a9ac-c3559136642a

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/18b1efba-40d6-48a0-a884-fd91b9b79df7

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/1f8e6b6a-9b58-42de-bba4-1675db62f126

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/4638171c-3218-4bf0-af68-d762778aa7ff

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/4704c49a-9fc7-419f-b0e1-0fbffe584885

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/737afe58-ef5e-44c9-84cf-2bba5203d88e

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/80316f8f-6578-4450-97ef-137ff5d04db0

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/c93ceb0e-0ed0-43c4-bc87-c8abeca12ca6

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/d09f9f1a-2a51-487c-985d-9410ea926f05

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/e63ff142-39d8-4126-b426-d031f4ae582f

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/f2a3db30-40f1-449b-a0ac-79705bfb2833

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/f6ecb0b5-8e71-4cc5-97a5-09e3d9090efe

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/fcf77341-ee13-47db-bdf4-5cad24a9176f

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `public, max-age=3600`
  * Other Info: ``
* URL: https://firefox.settings.services.mozilla.com/v1/

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `max-age=3600`
  * Other Info: ``
* URL: https://firefox.settings.services.mozilla.com/v1/buckets/main/collections/mfcdm-origins-list/changeset%3F_expected=1750871406038

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `max-age=3600`
  * Other Info: ``
* URL: https://firefox.settings.services.mozilla.com/v1/buckets/monitor/collections/changes/changeset%3Fcollection=mfcdm-origins-list&bucket=main&_expected=0

  * Method: `GET`
  * Parameter: `cache-control`
  * Attack: ``
  * Evidence: `max-age=3600`
  * Other Info: ``


Instances: 18

### Solution

For secure content, ensure the cache-control HTTP header is set with "no-cache, no-store, must-revalidate". If an asset should be cached consider setting the directives "public, max-age, immutable".

### Reference


* [ https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html#web-content-caching ](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html#web-content-caching)
* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Cache-Control ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Cache-Control)
* [ https://grayduck.mn/2021/09/13/cache-control-recommendations/ ](https://grayduck.mn/2021/09/13/cache-control-recommendations/)


#### CWE Id: [ 525 ](https://cwe.mitre.org/data/definitions/525.html)


#### WASC Id: 13

#### Source ID: 3

### [ Retrieved from Cache ](https://www.zaproxy.org/docs/alerts/10050/)



##### Informational (Medium)

### Description

The content was retrieved from a shared cache. If the response data is sensitive, personal or user-specific, this may result in sensitive information being leaked. In some cases, this may even result in a user gaining complete control of the session of another user, depending on the configuration of the caching components in use in their environment. This is primarily an issue where caching servers such as "proxy" caches are configured on the local network. This configuration is typically found in corporate or educational environments, for instance.

* URL: https://firefox-settings-attachments.cdn.mozilla.net/bundles/startup.json.mozlz4

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/08a8f48e-5b5a-4593-9a91-5dcc5f5e514f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/18b1efba-40d6-48a0-a884-fd91b9b79df7

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/4638171c-3218-4bf0-af68-d762778aa7ff

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/4704c49a-9fc7-419f-b0e1-0fbffe584885

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/737afe58-ef5e-44c9-84cf-2bba5203d88e

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/c93ceb0e-0ed0-43c4-bc87-c8abeca12ca6

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/d09f9f1a-2a51-487c-985d-9410ea926f05

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/e63ff142-39d8-4126-b426-d031f4ae582f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/f2a3db30-40f1-449b-a0ac-79705bfb2833

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/f6ecb0b5-8e71-4cc5-97a5-09e3d9090efe

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/fcf77341-ee13-47db-bdf4-5cad24a9176f

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://firefox.settings.services.mozilla.com/v1/

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `HIT`
  * Other Info: ``
* URL: https://content-signature-2.cdn.mozilla.net/g/chains/202402/remote-settings.content-signature.mozilla.org-2026-01-27-09-17-39.chain

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Age: 903`
  * Other Info: `The presence of the 'Age' header indicates that a HTTP/1.1 compliant caching server is in use.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/0a25e3cf-57e3-4a0b-a44d-b7cb3ab73662

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Age: 920`
  * Other Info: `The presence of the 'Age' header indicates that a HTTP/1.1 compliant caching server is in use.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/0e2c24a9-7cd1-466a-a9ac-c3559136642a

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Age: 1`
  * Other Info: `The presence of the 'Age' header indicates that a HTTP/1.1 compliant caching server is in use.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/1f8e6b6a-9b58-42de-bba4-1675db62f126

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Age: 2946`
  * Other Info: `The presence of the 'Age' header indicates that a HTTP/1.1 compliant caching server is in use.`
* URL: https://firefox-settings-attachments.cdn.mozilla.net/main-workspace/tracking-protection-lists/80316f8f-6578-4450-97ef-137ff5d04db0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Age: 3296`
  * Other Info: `The presence of the 'Age' header indicates that a HTTP/1.1 compliant caching server is in use.`
* URL: https://firefox.settings.services.mozilla.com/v1/buckets/main/collections/mfcdm-origins-list/changeset%3F_expected=1750871406038

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Age: 0`
  * Other Info: `The presence of the 'Age' header indicates that a HTTP/1.1 compliant caching server is in use.`
* URL: https://firefox.settings.services.mozilla.com/v1/buckets/monitor/collections/changes/changeset%3Fcollection=mfcdm-origins-list&bucket=main&_expected=0

  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Age: 0`
  * Other Info: `The presence of the 'Age' header indicates that a HTTP/1.1 compliant caching server is in use.`


Instances: 20

### Solution

Validate that the response does not contain sensitive, personal or user-specific information. If it does, consider the use of the following HTTP response headers, to limit, or prevent the content being stored and retrieved from the cache by another user:
Cache-Control: no-cache, no-store, must-revalidate, private
Pragma: no-cache
Expires: 0
This configuration directs both HTTP 1.0 and HTTP 1.1 compliant caching servers to not store the response, and to not retrieve the response (without validation) from the cache, in response to a similar request.

### Reference


* [ https://datatracker.ietf.org/doc/html/rfc7234 ](https://datatracker.ietf.org/doc/html/rfc7234)
* [ https://datatracker.ietf.org/doc/html/rfc7231 ](https://datatracker.ietf.org/doc/html/rfc7231)
* [ https://www.rfc-editor.org/rfc/rfc9110.html ](https://www.rfc-editor.org/rfc/rfc9110.html)


#### CWE Id: [ 525 ](https://cwe.mitre.org/data/definitions/525.html)


#### Source ID: 3

### [ Session Management Response Identified ](https://www.zaproxy.org/docs/alerts/10112/)



##### Informational (Medium)

### Description

The given response has been identified as containing a session management token. The 'Other Info' field contains a set of header tokens that can be used in the Header Based Session Management Method. If the request is in a context which has a Session Management Method set to "Auto-Detect" then this rule will change the session management to use the tokens identified.

* URL: http://localhost:8003/login

  * Method: `GET`
  * Parameter: `csrf_token`
  * Attack: ``
  * Evidence: `csrf_token`
  * Other Info: `cookie:csrf_token`
* URL: http://localhost:8003/register

  * Method: `GET`
  * Parameter: `csrf_token`
  * Attack: ``
  * Evidence: `csrf_token`
  * Other Info: `cookie:csrf_token`
* URL: http://localhost:8003/login

  * Method: `POST`
  * Parameter: `session_id`
  * Attack: ``
  * Evidence: `session_id`
  * Other Info: `cookie:session_id`
* URL: http://localhost:8003/login

  * Method: `GET`
  * Parameter: `csrf_token`
  * Attack: ``
  * Evidence: `csrf_token`
  * Other Info: `cookie:csrf_token`
* URL: http://localhost:8003/login

  * Method: `GET`
  * Parameter: `session_id`
  * Attack: ``
  * Evidence: `session_id`
  * Other Info: `cookie:session_id`


Instances: 5

### Solution

This is an informational alert rather than a vulnerability and so there is nothing to fix.

### Reference


* [ https://www.zaproxy.org/docs/desktop/addons/authentication-helper/session-mgmt-id/ ](https://www.zaproxy.org/docs/desktop/addons/authentication-helper/session-mgmt-id/)



#### Source ID: 3


