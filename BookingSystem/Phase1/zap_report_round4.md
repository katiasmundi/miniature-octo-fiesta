# ZAP by Checkmarx Scanning Report BookingSystem-Phase3 Kati

ZAP by [Checkmarx](https://checkmarx.com/).


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 0 |
| Medium | 0 |
| Low | 0 |
| Informational | 2 |




## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- |
| Authentication Request Identified | Informational | 3 |
| Session Management Response Identified | Informational | 5 |




## Alert Detail



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


