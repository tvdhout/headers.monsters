# Security headers glitch in Nginx

This repository includes a simple [nginx configuration](nginx/nginx.conf) which adds security headers by default.

In the location block I include an if-statement which adds additional headers if the request is a GET request. 

As a result, all the previously added headers are removed in the browser, but not in CURL. This results in [the website](https://headers.monster) scoring 100% on internet.nl, while in reality it does support the security headers.

The results on [securityheaders.com](https://securityheaders.com) are correct, because they do not use CURL but some automated browser agent (like selenium)
