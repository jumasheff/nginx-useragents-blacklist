# What is this?
The file useragents.rules contains a list of undesirable user-agents, which you want to keep out of your website(s).
#Usage
1. Put this file into /etc/nginx/ dir (in Ubuntu), so that it is accessible by this path: /etc/nginx/useragents.rules
2. In the main nginx config (/etc/nginx/nginx.conf), in the **http** section put this line: ```include /etc/nginx/useragents.rules;```
3. In the site config (/etc/nginx/sites-available/yoursite), in the **server** section put these lines:
```
if ($badagent) {
	return 403;
}
```
#Credits
[Dan Nanni](http://ask.xmodulo.com/block-specific-user-agents-nginx-web-server.html)
