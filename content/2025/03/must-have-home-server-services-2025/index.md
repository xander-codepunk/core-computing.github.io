---
title: 'MUST have Home Server Services'
date: '2025-03-07'
url: must-have-home-server-services-2025
draft: false
authors:
  - "Brandon Hopkins"
categories:
  - "Software"
tags:
  - "Homelab"
  - "Docker"
  - "Self-Host"
---
It’s been over an year since my last home server services tour. Since then quite a bit has changed. In this article we will overall all the services and applications I am running on my home server, discuss alternatives, and the overall structure of my ecosystem.

{{< alert >}}
**Warning!** This article is activily being worked on. Bare with me. :)
{{< /alert >}}

## My Setup

Last time around I had a variety of systems keeping everything going this included two NAS systems running Proxmox and Unraid, and then a Intel NUC running Ubuntu Server. Since then we have ditched Unraid in favor using two separates NAS systems together in a Proxmox Node.

The first node is running on a ZimaCube is this responsible for all my media servers and management. Additionally it has a windows virtual machine that I can spin up when needed. The second node is virtually everything else running on a single LXC with docker or running independently from a community installation script. I hope in the future to build my own server as to rid my use of desktop NAS systems, granted they have been great thus far.

![](/images/00_proxmox.png)

In my network I also have two Raspberry Pis. One of them is a Pi 5 with a PoE HAT and that is responsible for a Twingate connector and updating my IP address on Cloudflare. The other is hooked up to a 3D printer running Octoprint.

## Dashboards

Dashboard are used to create a simple webpage with links to all the services, websites, or really anything you care about. What makes each dashboard special and unique is the features they come with. Many can act as monitoring tools, have widgets to get more details from services, weather, and more.

### Glance

![](/images/01_glace-dashboard.png)

This dashboard is a new addition for me, it’s not the most feature rich of the options out there, but for me it’s simplistic and default look and feel is what stands out to me. You can use it to monitor and link to all your applications, like most tools in this category, but it also is great for monitoring various feeds, websites, and a customizable RSS feed. I use the tool as a start page for my web browser and it gives a quick and simple _glance_ of everything that I care about. One of the best things about it, in my opinion, is that everything is customized and configured in a simple yaml file.

**Resources:** [Video](https://youtu.be/QGONe-NTWuI) | [Github](https://github.com/glanceapp/glance)

### Homarr

{{< youtube A6vcTIzp_Ww >}}

I’m not using this one at the moment, but it’s currently a VERY CLOSE second for me. This one is more feature rich than Glance as it has much more widgets and is customizable though the graphical interface of the application. Homarr has it’s main focus in the name and that is a deep integration with the \*arr stack of applications. This dashboard, like Glance, can be used to monitor the up status of your applications, but it also integrates easily with Docker, Proxmox and other platforms.

**Resources:** [Video](https://youtu.be/A6vcTIzp_Ww) | [Github](https://github.com/homarr-labs/homarr) | [Website](https://homarr.dev/)

## Tools and Utilities

### File Browser

![](/images/02_file-browser.png)

This is another new addition, while not great for moving or copying large amounts of data, it has helped me significantly jumping though my rather large media server. Features rather simple and straight forward file management features, as described on their official website; “File Browser is a **create-your-own-cloud-kind** of software where you can install it on a server, direct it to a path and then access your files through a nice web interface. You have many available features!”

**Resources:** [Github](https://github.com/filebrowser/filebrowser) | [Website](https://filebrowser.org/)

### Vaultwarden

![](/images/03_vaultwarden-password-manager.png)

After being suggested this for YEARS I finally bit the bullet and have a self-hosted password vault. It’s fully compatible with Bitwardens extensions and applications, this allows be to keep all my passwords, emails, and payment information in one place.

**Resources:** [Github](https://github.com/dani-garcia/vaultwarden)

### Hoarder

![](/images/04_hoarder-bookmark-manager.png)

My video covering Hoarder may have turned into a unfortunate story of drama, that’s not to take away from how awesome this tool actually is. I think of it as a dumping ground for anything I come across that is slightly interesting. This is a self-hostable bookmark-everything app with a touch of AI for the data hoarders out there. Some of the features include the ability to take simple notes and store images and pdfs, automatic fetching for link titles, descriptions and images, sorting tools, and full text search of all the content stored.

**Resources:** [Video](https://youtu.be/TDWombBvK8c) | [Github](https://github.com/hoarder-app/hoarder) | [Website](https://hoarder.app/)

### Portainer

![](/images/05_portainer-docker-manager.png)

I’ll admit, I do have plans to slowly remove Portainer from my home server. I’ve gotten conformable enough with using docker compose and other Docker features in the command line that is almost slows me down. With that said Portainer is a GREAT tool for managing Docker stacks, containers, and other instances on other machines.

**Resources:** [Video](https://www.youtube.com/watch?v=olUD_F37n0E) | [Github](https://github.com/portainer/portainer) | [Website](https://docs.portainer.io/start/install-ce)

### Cockpit

![](/images/06_cockpit-server-tool.png)

Cockpit is one of the best tools that you can use to give your server a nice web interface to monitor and manage. Their website says; “See your server in a web browser and perform system tasks with a mouse. It’s easy to start containers, administer storage, configure networks, and inspect logs. Basically, you can think of Cockpit like a graphical “desktop interface”, but for individual servers.”

I was using this in a centralized LXC for managing shares and using various extensions to give cockpit even more features. After a very resent change in my home server setup I yet to install it on anything, but I’m leaving it here on this list as it is an amazing tool.

**Resources:** [Video](https://youtu.be/zLFB6ulC0Fg?si=9eFVzVcAebZUTgFi&t=1072) | [Github](https://github.com/cockpit-project/cockpit) | [Website](https://cockpit-project.org/)

### Octoprint

![](/images/07_octoprint-3d-printing.png)

Octoprint is another great tool that has actually helped me increase the use of my 3D printer. I have this software setup on a Raspberry Pi 4 plugged directly into the printer. Essentially turning my dumb 3D printer smart. This allow control of all aspects of 3D printing including, uploading gcodes, printing, monitoring, and much more. Setting up camera monitoring and video recording is a simple as plugging in a webcam.

**Resources:** [Github](https://github.com/OctoPrint/OctoPrint) | [Website](https://octoprint.org/)

## Media Server

### Jellyfin

![](/images/08_jellyfin-media-server.png)

Jellyfin is by far the best free and open source media server on the market right now. It has all the features you’d expect without any paywalls. This includes streaming to a wide variety of platforms. I currently run Jellyfin as a backup to Plex as that is currently my preferred platform. See the video about for much more information.

**Resources:** [Video](https://www.youtube.com/watch?v=eJvQKLVrmU8) | [Github](https://github.com/jellyfin/jellyfin) | [Website](https://jellyfin.org/)

### Plex

![](/images/09_plex-media-server.png)

Plex is my main media streaming platform. I have quite a few family members using it and Plex has support for more platforms and easier login capabilities. I’ve also recent setup a TV tuner and it has been working great. Another reason why I use Plex is the support for 3rd party tools such as Tautulli that we will get into below.

**Resources:** [Video](https://youtu.be/lXcfKTNObOo) | [Github](https://github.com/plexinc) | [Website](https://www.plex.tv/)


### Tautulli

![](/images/10_tautulli-plex-stats.png)

While Plex does have some statistics and logs to see what’s going on, it is nothing compared to what we get from Tautulli. From their website; “Tautulli is a 3rd party application that you can run alongside your Plex Media Server to monitor activity and track various statistics. Most importantly, these statistics include what has been watched, who watched it, when and where they watched it, and how it was watched.” This data is very helpful when I clean up and remove some media from the server. One of my favorite features of all this is the newsletter option that you can setup giving the users a overview of new media that has been added to the server.

https://tautulli.com/

## Media Management

Many of the applications below act in similar function with a slightly different goal or media type so the descriptions will be brief. With that these tools are by far some of my favorites in my home server.

### Overseerr

![](/images/11_overseerr-media-reuests.png)

Overseerr is an amazing tool for discovering new movies and shows as well as having Plex users request media they want to see. Overseerr integrates really well into Plex and some of the other services in this category. It can see what is already in your media library and if a request is made it can automatically add that entry to Radarr or Sonarr. I particularity like it because of the discover functionality, you can filter movies and shows by what streaming service they’re on, rating, and more.

https://overseerr.dev/

### Radarr

![](/images/12_radarr-movie-management.png)

Radarr is a media organization tool for movies. This allows you see scan your library to see everything you have. Manage file file names, see the media quality, and even search indexers for media. From their wiki; “Radarr is a movie collection manager for Usenet and BitTorrent users. It can monitor multiple RSS feeds for new movies and will interface with clients and indexers to grab, sort, and rename them. It can also be configured to automatically upgrade the quality of existing files in the library when a better quality format becomes available.”

https://radarr.video/

### Sonarr

![](/images/13_sonarr-shows-management.png)

This does all the same things as Radarr but with TV shows and series. It uses TVDB to see if you’re missing any episodes and even specials. From their wiki; “Sonarr is a PVR for Usenet and BitTorrent users. It can monitor multiple RSS feeds for new episodes of your favorite shows and will grab, sort and rename them. It can also be configured to automatically upgrade the quality of files already downloaded when a better quality format becomes available.”

https://sonarr.tv/

### Lidarr

![](/images/14_lidarr-music-management.png)

This acts the same as Radarr and Sonarr, but for music. From their wiki; “Lidarr is a music collection manager for Usenet and BitTorrent users. It can monitor multiple RSS feeds for new tracks from your favorite artists and will grab, sort and rename them. It can also be configured to automatically upgrade the quality of files already downloaded when a better quality format becomes available.”

https://lidarr.audio/

### Bazarr

This also acts similar to the other \*arr application, but with a focus on subtitles. From the Bazarr site; “Bazarr is a companion application to Sonarr and Radarr that manages and downloads subtitles based on your requirements. \[With manual search to\] find all the matching subtitles, choose the one you want and download it to your media directory with the proper name to be used by your media player.”

https://www.bazarr.media/

### Prowlarr

![](/images/15_prowlarr-index-manager.png)

Without using Prowlarr you’d need to manually setup your trackers and indexers in each application. This allows a centralized place to manage that aspect of these tools if you’re using it in this way. From their wiki; “Prowlarr is an indexer manager/proxy built on the popular arr .net/reactjs base stack to integrate with your various PVR apps. Prowlarr supports management of both Torrent Trackers and Usenet Indexers. It integrates seamlessly with [LazyLibrarian](https://lazylibrarian.gitlab.io/), [Lidarr](https://wiki.servarr.com/lidarr), [Mylar3](https://github.com/mylar3/mylar3), [Radarr](https://wiki.servarr.com/radarr), [Readarr](https://wiki.servarr.com/readarr), and [Sonarr](https://wiki.servarr.com/sonarr) offering complete management of your indexers with no per app Indexer setup required (we do it all).”

https://prowlarr.com/

## Download Clients

### qBittorrent

![](/images/16_qbittorrent-peer-client.png)

This is a web version of the popular qBittorrent peer-to-peer file sharing client. Overall its clean, simple, and has a fair bit of features. Works well with AirVPN (my favorite VPN service) and integrates well with various \*arr applications.

https://www.qbittorrent.org/

### NZBGet

![](/images/17_nzbget-newsletter-client.png)

This is a Usenet client written is C++. It works very well and out of any that I’ve used it seems to give the least amount of issues. This can pull files, fix them in some cases is the health is low, rename and move files.

https://nzbget.net/

## Files and Images

### Nextcloud

![](/images/18_nextcloud-cloud.png)

Nextcloud is the best in the game for replacing cloud services like Google Drive, Onedrive, and so on. Not only can it act as a great on-premise cloud, but there are many other add-ons and features that it offers. This includes a complete groupware suite, collaborative document editing, tasks, and much more.

https://nextcloud.com/

### Immich

![](/images/19_immich-photo-backup.png)

This is arguably the most important application that I am running. This is what I’ve used to completely replace Google Photos. Myself and a few of my family members use this as their primary Photo back solution. It has a mobile app that supports easy backups and some other key features include facial recognition and a location map of your photos. From their website; “Easily back up, organize, and manage your photos on your own server. Immich helps you browse, search and organize your photos and videos with ease, without sacrificing your privacy.”

https://immich.app/

### Docmost

![](/images/20_docmost-personal-wiki.png)

This is a new addition and it’s actually how I’m initially drafting this entire article. In my hunt to replace Notion I’ve started using this. While I’m still on a hunt for a more one-to-one replacement this is doing the trick for now. This tool is used to manage your own personal wiki, knowledge base, and notes. The UI is clean, elegant, and simple.

https://docmost.com/

## Smart Home and Automation

### Home Assistant

![](/images/21_home-assistant-smart.png)

Home Assistant is a great tool that allows the connection of many devices in your smart home and integrate them together with a variety blueprints, automatons, and more. You can create custom dashboards, use their mobile app, and so much more I can’t even properly describe here how much this tool is capable of.

https://www.home-assistant.io/

### Frigate

![](/images/22_frigate-nvr.png)

Frigate is the best open source, self-hosted NVR option that I can find. For a while I was using Blue Iris, but I HATE that you have to use Windows. This tool shines with you hook it up with a Coral TPU for AI object detection. The interface is wonderful and it supports most of what you’d expect of an NVR. Granted depending on your cameras it may be difficult to configure and use all the features a camera may support, for example, two way audio.

https://frigate.video/

### Zigbee2MQTT

![](/images/23_zigbee2mqtt-smart-devices.png)

I was originally using this with Home Assistant as an add-on, but I’ve noticed it to be way more reliable if it is separated out. Zigbee2MQTT supports various Zigbee adapters and a bunch of devices.

https://www.zigbee2mqtt.io/

## DNS and Remote Connections

### Pi-Hole

![](/images/24_pi-hole-dns-sinkhole.png)

By far the most popular “DNS Sinkhole” a Domain Name Service that blocks certain DNS inquires. In the case of Pi-Hole it uses black lists full of domains associated with advertisements and tracking. For example, one of the most blocked domain on my server is [s2s.mparticle.com](https://www.mparticle.com/about-us/) a data collection firm. And with Pi-Hole I can investigate and figure out why this data collection company is being reached out to so much. This is in addition to the main use case of simple ad blocking. Pi-Hole has many other features I’ve yet to dive into, but it’s a wonderful tool that is worth tying out of anyone.

https://pi-hole.net/

### NGINX Proxy Manager

![](/images/25_nginx-proxy-manager.png)

NGINX Proxy Manager is a simple web based proxy manager for setting up and forwarding domain names to your services and generating SSL certifications. I use this for both local top level domains and exposing a few select services to the public internet.

https://nginxproxymanager.com/

### Twingate

Full disclosure, Twingate is one of the channel sponsors. This is a VPN alternative for remotely connecting to your home server. It works by spinning up a smaller connector on your local network, then you use a client to establish a secure peer-to-peer connection. All this is managed and verified through the Twingate cloud platform. Something I started using recently is the Twingate service API to connect with a headless client. Connecting to one headless service to another.

https://bit.ly/twingate1024

### Cloudflare DDNS

![](/images/26_cloudflare-ddns.png)

This is a very simple docker container used to update your public IP address within the Cloudflare A records using their API. I need to use this becuase my public IP is dynamic, meaning it will randomly and automatically change every few weeks or sometimes every few days. From their Github it’s; “A feature-rich and robust Cloudflare DDNS updater with a small footprint. The program will detect your machine’s public IP addresses and update DNS records using the Cloudflare API.”

https://github.com/favonia/cloudflare-ddns

## Data and Metrics

### Grafana

![](/images/27_grafana-dashboards.png)

Grafana is a BEAUTIFUL dashboard tool that can translate various databases into stunning graphs, charts, and presentation. There is a huge amount of integrations and custom dashboard that many people create for their specific use cases. You can easily add a connection and import a dashboard to display the data. The most popular is for the Node Exporter that you can see above.

https://grafana.com/

### TeslaMate

![](/images/28_teslamate-grafana.png)

TeslaMate is a tool that uses the Tesla API to gather every possible data point about the car. This includes trips, mileage, battery, elevation, and much more. This is a stack that includes Teslamate itself, a database, Grafana, and a few others.

https://github.com/teslamate-org/teslamate

### InfluxDB2

![](/images/29_influxdb2-data-explorer.png)

InfluxDB is described as; “Purpose-built database for all types of time series data at any scale.” This database tool has it’s own way to turn data into charts and graphs, but I’m primarily using it for helpful data from my Proxmox server and pulling that data to Grafana dashboards.

https://www.influxdata.com/

### Prometheus (with Node Exporter)

![](/images/30_proetheus-query-execute.png)

Like InfluxDB this is a data collection tool for monitoring and data analytics. This one this the most popular of what I’m using so there are a ton of different integrations and dashboards to pick from. The most popular and probably the easiest to setup is the Node Exporter, I have this installed and two Raspberry Pi systems for monitoring.

https://prometheus.io/

## Network and Internet

### Omada

![](/images/31_omada-is-slow.png)

TP-Link sent over a few Omada devices a while back and I have not yet tried any of the competitors, so don’t consider this as a full endorsement. Overall it has been working well and it’s easy to mange static addresses, label ports, manage PoE, and much more.

https://www.omadanetworks.com/us/business-networking/omada-controller-cloud-software/omada-software-controller/

### xFinity

xFinity is trash, but it’s my only option in my area. I mean Comcast as a company is SO bad that I’ve even considered paying double for Starlink with much worse ping.
