---
title: "Running your own Monero node"
parent: Tutorials
---

# Running your own Monero node

We strongly recommend running your own Monero node! Here is a simple guide for running a Monero node with Ubuntu.

## Select hardware

You don't need fancy hardware to run a node that only is meant to handle your basic personal use, but we recommend the following:

* At least 256 GB of storage on an SSD
* At least dual core, ideally quad core
* At least 2 GB of RAM, ideally 4 GB
* At least 10 Mbps connection, with at least 100 GB of monthly data

We recommend running the node on your **home network**.

## Install Ubuntu

You can use another OS, but we will use Ubuntu for this guide.

Download the [latest Ubuntu "LTS" release here](https://ubuntu.com/download/server). For this guide, we are using the command line only version.

You will need to add this image to a flash drive. Here are guides for the operating system you are currently using:

* [Windows](https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-windows)
* [MacOS](https://ubuntu.com/tutorials/create-a-usb-stick-on-macos)
* [Ubuntu](https://ubuntu.com/tutorials/create-a-usb-stick-on-ubuntu)

Attach the flash drive to your Monero node computer, and [boot from USB](https://lifehacker.com/how-to-boot-from-a-usb-drive-or-cd-on-any-computer-5991848).

Follow the instructions to install Ubuntu Server. After you are done, turn off the computer, remove the flash drive, and turn it back on. Make sure it boots to the newly installed Ubuntu operating system.

## Update and harden Ubuntu

Run these commands (one at a time) to update and harden Ubuntu:

```
sudo apt-get update && sudo apt-get upgrade -y
sudo apt-get install -y ufw curl
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker $USER
su - $USER
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow 18080/tcp
sudo ufw allow 18081/tcp
sudo ufw enable
```

These will install Docker and enable a firewall.

## Install monerod

The Monero node software is called `monerod`.

You will need to decide if you want other people to be able to use your node for syncing and sending transactions. Doing so is good for the Monero network, but it will cost you more bandwidth.

### If you DO want others to be able to access your node

Run the following command:

```
docker run -d --restart unless-stopped --name="monerod" -p 18080:18080 -p 18081:18081 -v bitmonero:/home/monero sethsimmons/simple-monerod:latest --rpc-restricted-bind-ip=0.0.0.0 --rpc-restricted-bind-port=18081 --no-igd --no-zmq --enable-dns-blocklist --public-node
```

### If you DON'T want others to be able to access your node

Select a username and a strong password. Replace `user:pass` at the end of the command below with your selected username and STRONG password. For example (**don't use this!**), replace it with `monero:ryfP3IsKG6uZRiXp9zRB`.

```
docker run -d --restart unless-stopped --name="monerod" -p 18080:18080 -p 18081:18081 -v bitmonero:/home/monero sethsimmons/simple-monerod:latest --rpc-bind-ip=0.0.0.0 --rpc-bind-port=18081 --no-igd --no-zmq --enable-dns-blocklist --rpc-login:user:pass
```

### For all cases

Copy/paste the following entire block as a single command:

```
docker run -d \
    --name watchtower --restart unless-stopped \
    -v /var/run/docker.sock:/var/run/docker.sock \
    containrrr/watchtower --cleanup \
    monerod tor
```

## Configuring your router firewall

If you want your Monero node to be reachable outside of your local network, you will need to enable port forwarding on your router.

You will need to forward these ports:

* 18080 (TCP only, not UDP)
* 18081 (TCP only, not UDP)

There are many router-specific guides on [portforward.com](https://portforward.com/router.htm).

Make sure to use a modern router from a reputable brand that is still getting security updates! Update the router firmware, and select a STRONG router password!

## Updates

Your Monero node will automatically update to the latest Monero version! You will want to periodically update Ubuntu:

```
sudo apt-get update && sudo apt-get upgrade -y
```

## Credits

Thanks to SethforPrivacy for their [node guide](https://sethforprivacy.com/guides/run-a-monero-node/) and their [Docker image](https://hub.docker.com/r/sethsimmons/simple-monerod).
