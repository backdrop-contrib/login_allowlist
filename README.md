Login allowlist
===============

Limit login access to your site to only certain users, protect against "lazy"
brute force attack and malicious malformed requests to the login form.

Features
--------

You can restrict login access to your site to only a few of all registered users
by creating a list of those who are allowed to do so.

A "lazy" brute-force attack can use a large number of non-duplicate IP addresses
with relatively infrequent requests (one or two in a few minutes)
and cannot be prevented by IP blocking.

This module reacts to such behavior by returning error 404 or 403 (you can
select which) to an attacker for any user login related activity:
- in case username or email is not in list of allowed;
- if login request is harmfully malformed, for example - executable code
injection attempt.

By enabling logging of all unwanted login attempts, you can get an idea of which
username / password pairs were used for brute force, IP and User-Agent string
used by the attacker's script.

Additionally, User-Agent strings used by attackers (also can be collected
from the module log) can be stored in block-list to reject further login requests.
**Note:** some patterns of blocked UA are added for you out of the box,
but if you think some of them are suitable for the site login, you can unblock them.

**Please note:** when this module enabled, only administrators can manage accounts
for users, like new user registration or password reset.

Installation
------------

Install this module using the official Backdrop CMS instructions at
https://backdropcms.org/guide/modules

Configuration
-------------

Configuration page is available via menu *Administration > Configuration >
User accounts > Login allowlist* (admin/config/people/login_allowlist).

Under the tab "Main settings" you can:

- allow login to all registered active users (enabled by default);
- or create a allowlist for some users as described under a corresponding field;
- change type of HTTP status code returning to an unwanted visitor.

Under the tab "Blocked User-Agents":

- block a User-Agent string:
    - enter unwanted User-Agent string (wildcarded part of the string can be used);

- unblock previously blocked User-Agent:
    - beside a User-Agent string, click "Unblock", then confirm unblocking.

License
-------

This project is GPL v2 software. See the LICENSE.txt file in this directory for
complete text.

Current Maintainer
------------------

Vladimir (https://github.com/findlabnet/)

Issues
------

For bug reports, feature or support requests, please use the module
issue queue at https://github.com/backdrop-contrib/login_allowlist/issues.

Note
----

This module is a renamed successor for version 1.x-1.0.10 of [my another module](https://backdropcms.org/project/login_whitelist)
with the aim of use inclusive naming.
