# What is this?
The file useragents.txt contains a list of undesirable user-agents, which you want to keep out of your website(s).  
The file useragents.rules wraps the list into a nginx format.
#Usage
1) Put useragents.rules into /etc/nginx/ dir (in Ubuntu), so that it is accessible by this path: /etc/nginx/useragents.rules
2) In the main nginx config (/etc/nginx/nginx.conf), in the **http** section put this line:
```
include /etc/nginx/useragents.rules;
```
3) In the site config (/etc/nginx/sites-available/yoursite), in the **server** section put these lines:
```
if ($badagent) {
	return 403;
}
```
4) Test your newly activated settings:
- Install Chrome UA Spoofer Chrome extension
- Add bots from useragents.txt to Chrome UA Spoofer (open your browser, right click on Chrome UA Spoofer icon, click "Options")
- Select a user-agent, and visit your site, you should see **403 Forbidden**


#Credits
[Dan Nanni](http://ask.xmodulo.com/block-specific-user-agents-nginx-web-server.html)
