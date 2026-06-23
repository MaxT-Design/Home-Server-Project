# Home-Server-Project
Documenting the personal project of setting up a home server on my network. Shows my first steps into linux, docker, improving my network skills.

Architecture & Blueprint:
This is running on an old mini pc, specifically the "HP EliteDesk 800 G1 Mini PC Intel Core i5-4590T 4GB RAM 128GB SSD Wi-Fi, Win 10" from ebay for £34.99. Additionally I also bought 2x8GB DDR3L Ram later for £35 of amazon. Initially I ran debian with casa os managing the dockers however after finding it inconvenient and hard to use, I switched to Proxmox running LXC's installed from the "https://community-scripts.org/" website. This led to me upgrading the RAM since proxmox uses 1GB of RAM on its own, extra LXC's like a minecraft server would benefit heavily from dedicating 8GB of RAM. I also attached a 300GB HDD from an old laptop I took apart and use it for storing large files like movies and music, the apps themselves are stored on the SSD for speed.

Services Hosted:
I initially did this to step away from cloud storage and subscriptions, and regain control of whats on my computers. Here are all of the apps I have installed currently:
Samba - allowing me to manage my servers HDD from my Windows PC.
Tailscale - Allows me to setup HTTPS connection and access media from outside the local network.
Nginx Proxy manager - sets up a reverse proxy, allowing me to direct urls to services
Jellyfin - For managing personal media like films and music I used, a self hosted Netflix.
Crafty controller - For hosting minecraft servers on my personal server.
Homarr - A customisable dashboard for easy links access.
I plan to try Vaultwarden, Actual budget, Immich and others in the future.

Network & Security setup:
I use Tailscale and SSL certificates to allow HTTPS connections to the server. All traffic goes through Nginx, which reads the port number and forwards it to the respective service. This setup was in the terminal, and I've added a text document of the steps I used to set up. This means only by being on my tailnet do you have access to my server, and every app uses a secure and unique password to access. 

Lessons Learnt:
As helpful as docker was for learning the basics of linux and running containers, I found proxmox to be a much more organised and strangely simpler to use. Perhaps if RAM is tight using server debian is better but I'd highly recommend using proxmox. I've also seen online that LXC runs better but for more details please read yourself (this blog is a good start: https://www.docker.com/blog/lxc-vs-docker/)
