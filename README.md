# maintain-wan-lease
Resolve problem with Asus Merlin routers in terms of release/renew of udhcpc. Namely if a modem such as the B818-263 drops eth0, then absent a udhcpc release/renew, a loss in internet connectivity can result. It seems by default Asus routers do not issue the appropriate udhcpc release/renew. This script resolves this in an efficient manner by monitoring the eth0 interface and reacting to changes as they occur.  

For background see here: 

http://www.snbforums.com/threads/router-not-getting-internet-back-after-wan-drop.71954/post-709554

http://www.snbforums.com/threads/problem-udhcpc-does-not-deconfig-upon-wan-cable-disconnect.74397/

One way to install is to place the script inside /jffs/scripts, chmod +x it

And then setup or edit 'post-mount' to include the line:

/jffs/scripts/maintain-wan-lease &

See here for details concerning setting up scripts in Asus Merlin:

https://github.com/RMerl/asuswrt-merlin.ng/wiki/User-scripts

To test, try manually unplugging eth0 and placing it back in the router. You should see the appropriate lines end up on the system log confirming release and renew. 

For further support, please consult the snbforums forum. 

See for example this post:

http://www.snbforums.com/threads/rt-ax88u-isps-dhcp-does-not-function-properly-but-manual-udhcpc-call-works.74457/post-749666
