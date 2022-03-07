# maintain-wan-lease
Resolve problem with Asus Merlin routers in terms of release/renew of udhcpc.

For background see here: 

http://www.snbforums.com/threads/problem-udhcpc-does-not-deconfig-upon-wan-cable-disconnect.74397/

One way to install is to place the script inside /jffs/scripts - see here:

https://github.com/RMerl/asuswrt-merlin.ng/wiki/User-scripts

And then setup or edit 'post-mount' to include the line:

/jffs/scripts/maintain-wan-lease &

For further support, please consult the snbforums. 

See for example this post:

http://www.snbforums.com/threads/rt-ax88u-isps-dhcp-does-not-function-properly-but-manual-udhcpc-call-works.74457/post-749666
