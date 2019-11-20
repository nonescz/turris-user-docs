# SSH Honeypot as a Service (HaaS)

[Honeypot as a Service](haas.nic.cz) is a publicly available service, which can be installed on PC, server with public IPv4 address and even on Turris routers. You can find there requirements and global statistics, which they show you how many users are participating, how many sessions were with or without commands and how many commands were issued today, map of attacks, public data and a lot more.

## What is a honeypot?

## Background

SSH is one of the most common protocols in the world for securely connecting to other machines, which run an SSH server. An SSH server is enabled on pretty much every home router and often without the user’s awareness. Sometimes Telnet is enabled instead of the SSH server, which is much worse security-wise because it sends and receives data in plaintext.

Because manufacturers very rarely update their firmware, the chances that you are running an outdated and vulnerable version of the SSH server are really high. From time to time news is released about new CVEs (Common Vulnerabilities and Exposures), such as #sambacry and #dirtycow. Most of the time, manufacturers don’t care if there is a security issue or even a back door and instead of trying to keep up an old device, the manufacturer will usually tell you to buy a new one.

For the purposes of knowing who the attackers are, what methods they use and from which IP addresses they conduct the attacks, we implemented an SSH honeypot. It’s basically a “fake” SSH server to which we deliberately allow the attackers to connect to and monitor their behavior.

__Information available to us:__
- From which IP address the attacker logged in
- Credentials he used to log in
- Attacker behavior
- The scripts, which the attacker ran in the honeypot

The more targets the attackers try to reach, the more information we get about the attackers and the bigger the chances that we can reveal them, block them (or fix affected devices) and publish information about them.

## Installation

To install and setup SSH honeypot on your Turris router proceed these steps:

1. In Foris web interface by using Updater tab install __SSH Honeypot__.
2. Create an account on [Honeypot as a Service website](https://haas.nic.cz).
3. After login in, add a new device and copy the token.
4. Token needs to be filled in the configuration file /etc/config/haas located on your router. __Otherwise SSH honeypot won't start__.
5. Start the service __haas_proxy__

## Pictures
### List of sessions

### Command list

## Move the SSH server to a port for remote administration

The data is further reduced in order to store it longer. Most importantly,
individual flows are aggregated. **Aggregation** simply means that instead of
storing many flows of the same host, the flows are merged together for a given
time frame. The total number of received and sent bytes is preserved, but some
detail about duration and start times of individual flows is lost. **The records
are kept for 4 weeks**, but we have plans to adjust this in the future.
