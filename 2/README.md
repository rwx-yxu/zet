# Access private machines via SSH

Currently, I am considering using a ssh tunnel to access my homelab
virtual machines from anywhere. The reason I would want this for my use case 
is to be able to access my dev machine from university for example to make my 
notes or dev work if I have a long gap between lectures (which I do have on most
 days) rather than going back home and then back to university. The university 
 doesn't intend to use WSL and are not interested in teaching terminal use case. 
 Another blocker is that the university computers do not persist storage once 
 logged out so I cannot download windows terminal or any client software as well.

I have looked at:
* Inlets pro[^2] - I have used this before to briefly host a web application
  on the internet before and I know how to use it. The major downside is
  the cost. I have to pay for a vm in the cloud as well the inlets
  subscription on top. Plus, I will only have 2 tunnels. The plus side
  is that I will have no vendor lock in.
* Tailscale[^2] - This is relatively new and it is good for a vpn like
  experience across your devices. You need to register them on the
  tailscale network first. This means that the host machine and incoming
  machine needs to tailscale client to authenticate for their network.
  The plus side to this is that I know exactly what devices are allowed
  to connect. As well as this, tailscale has no cost for personal use.
  The blocker for this would be that I need to download the windows
  tailscale client on the university machine which I cannot do. The
  tailscale user experience is really seamless otherwise.
* Cloud flare tunnel[^2] - Cloud flare tunnel is also a free solution like
  tailscale but the endpoint will be publicly accessible from the
  internet. The key difference with cloud flare tunnels is that you can
  browser render a terminal without any setup. All you need to do is
  access the public domain which I have. I decided to go with this
  option because it means all I need to do is hit a public host name.

Setting up cloud flare tunnels involves more steps than the other two
options. The documentation is lacking because of the products on
display.
  * First, you must have the name servers for your domain to use
    Cloudflare's only. The name servers cannot be anyone elses. I did
    have digital oceans name servers as well as cloudflares but that
    does not work. This is to add your domain to cloudflares
  * Cloud flare has the cloudflare site account but also a cloud flare
    zero trust account with different dashboards... First add the site
    to cloud flare then go to cloud flare zero trust.
  * Ensure that the site is active on cloud flare first before add in a
    tunnel on zero trust.
  * On zero trust, you have a tunnel and also applications. As far as I
    can tell, the tunnel does the actual routing of the tunnel using the
    domain to the host machine. An application sets up the access rules
    and policies. Both are required.

I noticed that the browser rendered colours are a bit off due to the
lack of custom colouring being set from the terminal (which I use
windows terminal). But, I can ssh into my homelab now from a single URL.
Auth is done by a pin code.

Overall, I am happy with how this turned out because It means that I can
use my home dev vm at university. I also noticed that since you can set
routing with tunnels, I can expose other things as well such as a github
hook or applications on my network!

[^2]:https://docs.inlets.dev/tutorial/ssh-tcp-tunnel/
[^2]:https://tailscale.com/kb/1193/tailscale-ssh/
[^2]:https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/use_cases/ssh/#connect-to-ssh-server-with-cloudflared-access
