pxbp
====

A php proxy for xmpp bosh communication.  For those who cant or dont want to setup mod_proxy


I found it annoying to setup apache or other webservers to proxy XMPP Bosh 
connections to the XMPP server.

Since the XMPP clients web server is usually never the same box as the XMPP 
server and javascript does not like to make requests to different IPs because 
of cross site scripting problems. It seemed the only really solution was to 
have the webserver setup a proxied connection to the XMPP bosh port/ip.

Not anymore. Now through the use of a simple PHP script and curl you can proxy 
the requests with out having to enable mod_proxy in apache. 


To use this script make sure php and it has support for curl (php5-curl).
Put the script somewhere, anywhere you want on your web server, then
configure your XMPP Binding/BOSH webapp to use this script as the base
url location for the binding interface.  In JWChat this would look like
httpbase:"/bosh_proxy.php"
if the file was off the webroot.

You will also need to edit the bosh_proxy.php script to point to the correct
location for your XMPP BOSH server.  Feel free to setup logging, but it is
very verbose and probably will not want to keep it on once you get it 
working.


Email any requests or bugs to lwahlmeier@gmail.com.  Please put
php-xmppbosh-proxy in the subject line.


