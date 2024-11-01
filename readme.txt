=== Plugin Name ===
Contributors: gpaterno
Donate link: 
Tags: otp, security
Requires at least: 3.0
Tested up to: 3.3.1
Stable tag: trunk

This is a plugin to autheticate users through the SecurePass One Time Passwords service.

== Description ==

A lot of web sites, even well known ones (newspapers, telcos, ...) adopts 
WordPress as their CMS. WordPress is a great platform, however it
can happen that password leaking or guessing might lead to unauthorized
access to the platform. A potential attacker can be therefore able to 
change articles, part of the web site and/or make the website unavailable,
with image and economic damages for a company or for a blogger.
This is even more true if your website is not SSL protected.

SecurePass is a SaaS service offering an easy and affordable solution
for One Time Passwords (OTP) and strong authentication in general. They 
offer 5 users for free included with their standard (=basic) account, which
is more than enough for standard blogs and web sites. Companies can purchase
additional users, if needed.

More information on the section "Setup and configure SecurePass" in Other Notes.
To open a SecurePass account go to http://www.secure-pass.net/open


== Installation ==

1. Create a 'wp-securepass' directory in '/wp-content/plugins/'
2. Copy 'securepass.php' and 'radius.class.php' in '/wp-content/plugins/wp-securepass/'
3. Open the file 'securepass.php' and change the variable $radius_secret with your own secret as set in SecurePass admin
4. Create a local user that matches a user in SecurePass. Note: The admin user will be no longer checked locally.
1. Activate the plugin through the 'Plugins' menu in WordPress

= More information =
Edit the securepass.php file and change $radius_secret variable to reflect
the secret password as specified in the "Device" specified in the SecurePass
administration panel. The variable $radius_host contains the primary
RADIUS server of SecurePass, located in Switzerland (Lugano). 
A secondary RADIUS is available in Italy (Milan), if you prefer this
location change $radius_host to 'radius2.secure-pass.net'.

WARNING!!! Before activating this plugin, create an user in wordpress that
matches a username in SecurePass and grant full administrative powers.
This because the admin user will be no longer checked locally. In case you 
won't be able to login anymore, a workaround is moving the securepass plugin 
directory to another directory name, ex: "mv securepass securepass.old".


== Changelog ==

= 0.1 =
Initial code of the plugin


== Setup and configure SecurePass ==
If you don't own already an account with SecurePass, you can sign-up for a new account here: http://www.secure-pass.net/open

Note: Use "misec2011" as promo code, it will give you an entitlement for using 
SecurePass up to 10 users for 2 years free-of-charge. Without any promo code,
you will have 5 users for 20 years for free. It depends on what you need (more users or more years).

Connect to the admin interface on https://admin.secure-pass.net 
and create a new device (basically a RADIUS client). 

In the admin interface, go to the "Device" section and add a new device. 
You will need to set the public IP Address of the server, a fully qualified 
domain name (FQDN), and the secret password for the radius authentication. 
It's ok if your web server is behind a firewall and/or NAT, ensure that
your server has rights to send (and receive) RADIUS authentication requests,
i.e. UDP port 1812.

== Further reading ==

* This plugin web site: 
  https://github.com/gpaterno/wp-securepass/

* SecurePass web site: 
  http://www.secure-pass.net/

* UK on-line shop for SecurePass (they sell hardware tokens):
  http://shop.nervinesecurity.com/

