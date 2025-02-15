# Netlas scripts
## About
In this repository, you can find some scripts that use [Netlas.io](https://netlas.io) search engine. Some of them may be of interest to pen testers or bug bounters, and some to enthusiasts in the field of information security. And some will simply allow you to spend time with interest, studying various objects on the vast Internet.
***
## Installing
*Note*: Guide for Debian/Ubuntu only.
1. Make sure you have bash installed. If not, install it first by running the following commands in the Terminal:  
`$ sudo apt update`  
`$ sudo apt upgrade`  
`$ sudo apt install bash-completion`  

2. Install Netlas CLI and save your API Key to your local device  
`$ pip install netlas`  
`$ netlas savekey [APIKEY]`  
*Note*: more about Netlas CLI you can read [here](https://github.com/netlas-io/netlas-python).  

3. Clone this repository  
`$ git clone https://github.com/netlas-io/netlas-scripts.git`  
4. Open the created directory  
`$ cd netlas-scripts`   

***
## Scripts

### Netlas domains and IP recon script

Use this script to passively extend an atack surface of any target. It gets a files with domains, subdomains, IP addresses and CIDRs as an input info and returns a list of domains, subdomains and IP addresses that are also related to the target. Read more about how it works in this [article](https://netlas.medium.com/fast-one-shot-passive-recon-script-with-netlas-io-53a75b018fcc).

**Usage:** 

`user@host:~$ bash netlas_domains_and_ip_recon.sh domains_IPs_CIDRs.txt`

**Output files:**

- **domains_from_netlas.txt** - a list of domains and subdomains, having at least one A-record, which was found;
- **ips_from_netlas.txt** - a list of A-records.
***
### Netlas download http responses script
Use this script to download web pages available in Netlas.io Responses Search tool. It gets a files with domains, subdomains and IP addresses as an input and returns a set of html files associated with these targets.

This script takes as input the files obtained as a result of the work of the previous one and loads all the pages from all objects, which will later automatically check them for vulnerabilities. Read more about how it works in this [article](https://netlas.medium.com/fast-one-shot-passive-recon-script-with-netlas-io-53a75b018fcc).

**Usage:**

`user@host:~$ bash netlas_download_http_responses.sh domains_from_netlas.txt ip_from_netlas.txt`  

**Output files:**

**./responses/domain-443_page_path_!200.html** - directory with .html files, where:

- `domain` – a target host from input file;
- `443` – a port number;
- `_page_path_` – a path on the server, where this page is located (slashes replased by "_");
  in this case page downloaded from https://domain:443/page/path/
- `!200`– an HTTP server response code.

***



## Follow us

[Twitter](https://twitter.com/Netlas_io), [Telegram](https://t.me/netlas), [Medium](https://medium.com/@netlas), [Linkedin](https://www.linkedin.com/company/netlas-io/), [Facebook](https://www.facebook.com/Netlas.io)
