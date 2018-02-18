Apache httpd 2.4.29 Released
Changes with Apache 2.4.29

*) mod_unique_id: Use output of the PRNG rather than IP address and pid, avoiding sleep() call and possible DNS issues at startup, plus improving randomness for IPv6-only hosts. [Jan Kaluza]

*) mod_rewrite, core: Avoid the 'Vary: Host' response header when HTTP_HOST is used in a condition that evaluates to true. PR 58231 [Luca Toscano]

*) mod_http2: v0.10.12, removed optimization for mutex handling in bucket beams that could lead to assertion failure in edge cases. [Stefan Eissing]

*) mod_proxy: Fix regression for non decimal loadfactor parameter introduced in 2.4.28. [Jim Jagielski]

*) mod_authz_dbd: fix a segmentation fault if AuthzDBDQuery is not set. PR 61546. [Lubos Uhliarik ]

*) mod_rewrite: Add support for starting External Rewriting Programs as non-root user on UNIX systems by specifying username and group name as third argument of RewriteMap directive. [Jan Kaluza]

*) core: Rewrite the Content-Length filter to avoid excessive memory consumption. Chunked responses will be generated in more cases than in previous releases. PR 61222. [Joe Orton, Ruediger Pluem]

*) mod_ssl: Fix SessionTicket callback return value, which does seem to matter with OpenSSL 1.1. [Yann Ylavic]

[Apache 2.3.0-dev includes those bug fixes and changes with the Apache 2.2.xx tree as documented, and except as noted, below.]

Changes with Apache 2.2.x and later:

*) http://svn.apache.org/viewvc/httpd/httpd/branches/2.2.x/CHANGES?view=markup

Changes with Apache 2.0.x and later:

*) http://svn.apache.org/viewvc/httpd/httpd/branches/2.0.x/CHANGES?view=markup

Apache httpd 2.2.34 Released End-of-Life
Changes with Apache 2.2.34 (final)

*) SECURITY: CVE-2017-9788 (cve.mitre.org) mod_auth_digest: Uninitialized memory reflection. The value placeholder in [Proxy-]Authorization headers type 'Digest' was not initialized or reset before or between successive key=value assignments. [William Rowe]

*) Allow single-char field names inadvertantly disallowed in 2.2.32. PR 61220. [Yann Ylavic]

Changes with Apache 2.2.33 (not released)

*) SECURITY: CVE-2017-7668 (cve.mitre.org) The HTTP strict parsing changes added in 2.2.32 and 2.4.24 introduced a bug in token list parsing, which allows ap_find_token() to search past the end of its input string. By maliciously crafting a sequence of request headers, an attacker may be able to cause a segmentation fault, or to force ap_find_token() to return an incorrect value. [Jacob Champion]

*) SECURITY: CVE-2017-3169 (cve.mitre.org) mod_ssl may dereference a NULL pointer when third-party modules call ap_hook_process_connection() during an HTTP request to an HTTPS port. [Yann Ylavic]

*) SECURITY: CVE-2017-3167 (cve.mitre.org) Use of the ap_get_basic_auth_pw() by third-party modules outside of the authentication phase may lead to authentication requirements being bypassed. [Emmanuel Dreyfus , Jacob Champion, Eric Covener]

*) SECURITY: CVE-2017-7679 (cve.mitre.org) mod_mime can read one byte past the end of a buffer when sending a malicious Content-Type response header. [Yann Ylavic]

*) Fix HttpProtocolOptions to inherit from global to VirtualHost scope. [Joe Orton]

Looking Forward to NGINX 1.13
The NGINX 1.13 release series also promises to bring significant advances, including enhancements to HTTP/2 and caching capabilities. We will also be making continual improvements to nginScript in terms of JavaScript language support and to enable even more sophisticated programmatic configuration. The demands of modern, distributed, microservices applications are also driving part of our roadmap, and more will be shared at our annual user conference, nginx.conf 2017, this September 6–8 in Portland, OR.

NGINX 1.11 in Review
The past year was another busy one for NGINX development. We added a number of new features and capabilities to the 1.11 mainline branch: dynamic modules, IP Transparency, improved TCP/UDP load balancing, better caching performance, and more.

WordPress 4.9.4 is now available.
This maintenance release fixes a severe bug in 4.9.3, which will cause sites that support automatic background updates to fail to update automatically, and will require action from you (or your host) for it to be updated to 4.9.4.

Four years ago with WordPress 3.7 “Basie”, we added the ability for WordPress to self-update, keeping your website secure and bug-free, even when you weren’t available to do it yourself. For four years it’s helped keep millions of installs updated with very few issues over that time. Unfortunately yesterdays 4.9.3 release contained a severe bug which was only discovered after release. The bug will cause WordPress to encounter an error when it attempts to update itself to WordPress 4.9.4, and will require an update to be performed through the WordPress dashboard or hosts update tools.

WordPress managed hosting companies who install updates automatically for their customers can install the update as normal, and we’ll be working with other hosts to ensure that as many customers of theirs who can be automatically updated to WordPress 4.9.4 can be.

For more technical details of the issue, we’ve posted on our Core Development blog. For a full list of changes, consult the list of tickets.

Download WordPress 4.9.4 or visit Dashboard → Updates and click “Update Now.”

WordPress 4.9.3 is now available.
This maintenance release fixes 34 bugs in 4.9, including fixes for Customizer changesets, widgets, visual editor, and PHP 7.2 compatibility. For a full list of changes, consult the list of tickets and the changelog.

Download WordPress 4.9.3 or visit Dashboard → Updates and click “Update Now.” Sites that support automatic background updates are already beginning to update automatically.

Thank you to everyone who contributed to WordPress 4.9.3:

Aaron Jorbin, abdullahramzan, Adam Silverstein, Andrea Fercia, andreiglingeanu, Andrew Ozz, Brandon Payton, Chetan Prajapati, coleh, Darko A7, David Cramer, David Herrera, Dion Hulse, Felix Arntz, Frank Klein, Gary Pendergast, Jb Audras, Jeffrey Paul, lizkarkoski, Marius L. J., mattyrob, Monika Rao, munyagu, ndavison, Nick Momrik, Peter Wilson, Rachel Baker, rishishah, Ryan Paul, Sami Ahmed Siddiqui, Sayed Taqui, Sean Hayes, Sergey Biryukov, Shawn Hooper, Stephen Edgar, Sultan Nasir Uddin, tigertech, and Weston Ruter.
