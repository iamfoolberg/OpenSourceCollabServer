#Abrtract

#Target: build a collaborating enviroment with opensource projects

\#  including:

\#    Host virtualization, by Proxmox VE, and QEMU used by PVE, and so on

\#    remote login with VPN, by SoftEther

\#    NAT seperation with DHCP, by openwrt

\#    internal and external DNS server, by dnsmasq, smartDNS

\#    light-weight container manager, by Docker and Docker swarm, and registry, portainer

\#    service proxy, by nginx

\#    database backends, by MySQL, Postgres SQL, Redis, php adminer, ...

\#    all-in-one user passport, by openLDAP, FreeRadius, KeyCloak

\#    simple mail box, by apache james and roundcube

\#    simple text co-edit, by etherpad, and many plugins

\#    simple charts co-edit, by ethercalc

\#    office doc(.docx, .pptx, .xslx,...) co-edit, by OnlyOffice

\#    online visio-style drawer, draw.io

\#    simple portal CMS, by joomla

\#    SVG based graphics co-edit, by penpot and excalidraw

\#    image co-edit, by drawpile

\#    online workspace, by Humhub and NextCloud(with its plugins)

\#    learning manage system, by moodle and its plugins

\#    online chat, by synapse and element

\#    online conference, by Openmeetings and coturn, kurento

\#    p2p search engine, by yacy

\#    online survey system, by LimeSurvey

\#    online paper co-edit, FidusWriter

\#    --that’s NOT all, add other components as you wish

\#  required:

\#    a powerfull mini-server,

\#      with 64GB ECC RAM, CPU(s) with 16 cores, 1000M network card, 1TB or more SSD disk(s).

\#    a soft-router,

\#      with at least 4 1000M ports, 16GB RAM, 128GB SSD disk.

\#    a stable internet port and power supply.

\#    --that’s all.

\#     And the system is scalable,

\#       you can add more hardware for higher performance,

\#       and more components for better service.

\#       components available: nexus, gitlab, redmine, yourls, and so on

\#  arch:

\#    1. PVE virualizes the mini-server and soft-router, providing VMs needed.

\#    2. In soft-router, 3 VMs are created to handle the user access:

\#      outer-openwrt, make NAT-outer and enable users access the services inside the NAT

\#      vpn-openwrt, make NAT-vnp and enable users access the VPN

\#      vpn-softether, create a VPN server, enable the VPN clients to access services inside the NAT

\#    3.In mini-server, 2 VMs are created for docker swarm

\#      swarm-manager, labled with “infra”, run as manager

\#      swarm-worker, labled with “common”, run as worker

\#      --you can add more VMs to run docker swarm.

\#    4.All services are running as docker swarm services or stacks.

\#    5.All persistence data are provided by docker volumns or databases.

\#    6.A registry docker service is provided to manage custom docker images, and

\#      a portainer is provided to manage the (mini-) docker swarm cluster.
