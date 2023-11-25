![HomeLab](https://www.raspberrypi.org/app/uploads/2020/06/cropped-raspberrry_pi_logo-100x100.png) 
# HomeLab

This HomeLab project will configure a set of servers using Docker. The infrastructure uses a registered domain and is encrypted with SSL using LetsEncrypt. All traffic goes via Nginx Reverse Proxy. A private VPN is configured using Wireguard to allow remote access into the local network. The VPN uses a local DNS server which blacklists domains and prevents malicious attacks. The docker infrastructure is also monitored using a combination of Grafana, Prometheus and Cadvisor. A secured dashboard site is configure for access and management of the infrastructure. 

### The list of tools used within the environment.
- RaspberryPi
- Nginx Reverse Proxy Manager
- Portainer
- Pihole
- WireGuard VPN 
- UptimeKuma
- Grafana

### Setting up Raspberry Pi in the order of sequence:

1. Install the recommeneded Pi Operating System for your Pi. Using the [pi imager builder software](https://www.raspberrypi.com/news/raspberry-pi-imager-imaging-utility/) 

1. Update your OS with the latest rpm packages
```sudo apt update && sudo apt get upgrade --yes```

1. Install the required packages for docker
```sudo apt-get install libffi-dev libssl-dev vim --yes```

1. Set up ssh config for remote access. Configure port fowarding from the router to the private IP of the Raspberry Pi.

1. Reserve the assigned IP on the router so that it becomes the static IP for your Raspberry Pi.

1. Install docker and docker-compose binaries
   Reference: https://gist.github.com/troyfontaine

### Setup a registered domain

1. Register for a domain name. For example [hostinger](https://www.hostinger.com/). There are many other domains that you can register for free. For example [dnsduck](https://www.duckdns.org/) and [freedns](https://freedns.afraid.org/)

1. Setup [cloudflare](https://www.cloudflare.com/) in order to manage your registered domain. I would also advise setting up cloudflare DNSSEC.

### The next steps is to now to setup the environment

1. git clone this repository
```git clone git@github.com:Linux-Pingu/HomeLab.git```

1. Edit the .env files in each folder. Where you see the value ```changeme``` , change it to your own password.
   
1. Install and configure [nginx-proxy-manager](https://github.com/Linux-Pingu/HomeLab/tree/main/nginx)

1. Install and configure Portainer

1. Install and configure Pihole

1. Install and configure UptimeKuma
   
1. Install and configure Grafana
   
1. Install and configure Wiregaurd VPN

1. Install and configure Dashy

> [!NOTE]
> Once all the servers are installed, additional configuration is required to be done on Nginx with Letsencrypt, Pihole, UptimeKuma and Dashy. As this is dependent on your requirements.
