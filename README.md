# HomeLab
RaspberryPi , Nginx Proxy Manager, Pihole, WireGuard VPN, Portainer, UptimeKuma

The order of build is:

A. Build up Raspberry Pi
   1. Install relevent Pi os using pi imager build software
   2. sudo apt update && sudo apt get upgrade --yes
   3. sudo apt-get install libffi-dev libssl-dev vim --yes
   4. Set up ssh config remote access (port fowarding from router to private ip of pi)
   5. Reserve the assigned ip as a static ip for your device on your router

B. Register for a domain name on hostinger. There are many other ones out there for free as well

C. Setup cloudflare to manage your domain on hostinger. Including DNSSEC.

D. Install docker and docker-compose
    https://gist.github.com/troyfontaine
  

E. Install nginx-proxy-manager with letsEncrypt
   https://notthebe.ee/blog/easy-ssl-in-homelab-dns01

F. Install pihole

G. Install Wiregaurd VPN

H. Install cloudflare container to auto renew public IP addrress if it changes so there is no impact on your network

I. Intall uptimekuma and grafana to monitor your websites and containers performance.

G. Optional: setup auto notifications to your email if something serious gets picked up from monitoring.


 


      

