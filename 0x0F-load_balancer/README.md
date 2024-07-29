# 0x0F. Load Balancer

## Project Overview

In this project, you will configure a load balancing setup using HAProxy and Nginx to improve the redundancy and scalability of your web servers. You will use Bash scripts to automate the configuration of your web servers and load balancer. Additionally, you will work with Puppet for an advanced task.

## Tasks

### 0. Double the Number of Web Servers

**Objective:** Configure a new web server (`web-02`) to be identical to an existing one (`web-01`) and set up custom HTTP response headers.

- **Requirements:**
  - Configure Nginx on `web-01` and `web-02` to include a custom HTTP header.
  - The custom HTTP header should be `X-Served-By` with the value being the hostname of the server.
  - Create a Bash script `0-custom_http_response_header` to automate this configuration.

**Example:**
```bash
curl -sI 54.210.47.110 | grep X-Served-By
X-Served-By: [hostname]
```

### 1. Install Your Load Balancer

**Objective:** Install and configure HAProxy on `lb-01` to balance traffic between `web-01` and `web-02`.

- **Requirements:**
  - Configure HAProxy to distribute traffic using a round-robin algorithm.
  - Ensure HAProxy can be managed via an init script.
  - Create a Bash script `1-install_load_balancer` to automate this setup.

**Example:**
```bash
curl -Is 54.210.47.110
HTTP/1.1 200 OK
Server: nginx/1.4.6 (Ubuntu)
X-Served-By: [web-01 or web-02]
```

### 2. Add a Custom HTTP Header with Puppet (Advanced)

**Objective:** Automate the addition of a custom HTTP header using Puppet.

- **Requirements:**
  - The header should be `X-Served-By` with the hostname of the server.
  - Create a Puppet manifest `2-puppet_custom_http_response_header.pp` to configure this.

## Resources

- **Introduction to Load Balancing and HAProxy:** [Link](https://example.com)
- **HTTP Header:** [Link](https://example.com)
- **Debian/Ubuntu HAProxy Packages:** [Link](https://example.com)

## Your Servers

- **web-01**
  - **Username:** ubuntu
  - **IP:** 54.210.195.89
  - **State:** running

- **web-02**
  - **Username:** ubuntu
  - **IP:** 18.234.130.12
  - **State:** running

- **lb-01**
  - **Username:** ubuntu
  - **IP:** 54.144.136.159
  - **State:** running

## Requirements

- **Editors:** Allowed editors include vi, vim, emacs.
- **Ubuntu Version:** All files will be interpreted on Ubuntu 16.04 LTS.
- **File Requirements:**
  - All Bash script files must be executable.
  - Scripts must start with `#!/usr/bin/env bash` and a comment explaining their purpose.
  - Files must end with a new line.
- **Shellcheck:** Scripts should pass Shellcheck (version 0.3.7) without errors.

## File Structure

- **0-custom_http_response_header:** Script to configure Nginx with a custom HTTP header.
- **1-install_load_balancer:** Script to install and configure HAProxy.
- **2-puppet_custom_http_response_header.pp:** Puppet manifest for custom HTTP headers.

## How to Run

1. **For Bash Scripts:**
   - Make the script executable: `chmod +x script_name.sh`
   - Execute the script: `./script_name.sh`

2. **For Puppet Manifest:**
   - Apply the Puppet manifest: `puppet apply 2-puppet_custom_http_response_header.pp`

## README.md

This file provides a comprehensive overview of the project requirements, tasks, and how to execute the scripts. Make sure to follow the instructions closely to complete the project successfully.

