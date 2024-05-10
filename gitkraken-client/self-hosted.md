---

title: GitKraken On-Premise Self-Hosted Server
description: Learn about the installation of GitKraken On-Premise Self-Hosted Server
taxonomy:
    category: gitkraken-client

---

## Overview

**GitKraken On-Premise Self-Hosted Server** is the installed version of GitKraken Desktop that lives entirely within your network. It is also known as *GitKraken Enterprise Self-Hosted*, *GitKraken Enterprise On-Premise Server*, or simply *GitKraken Self-Hosted*. Its main use is to allow users to login without leaving your internal network.

Benefits of Self-Hosted Server:

- For use without internet
- Supports both built-in authentication using email as well as LDAP for user management
- Control version updates

<img src='/wp-content/uploads/manage-users.png' srcset='/wp-content/uploads/manage-users@2x.png 2x' class='img-bordered img-responsive center'>

## System Requirements

GitKraken Self-Hosted Server runs on a small spec Linux server (or virtual machine) inside Docker containers.

  * Requires a Linux server running on CentOS, Ubuntu, or Red Hat Enterprise Linux 7 (RHEL7).
  * The server needs to be able to run Docker CE with at least:
    * 2 cores
    * 4GB of RAM
    * 5GB of disk space

Here are [Docker's requirements](https://docs.docker.com/engine/installation/linux/docker-ce/centos/) for CentOS:

  * To install Docker CE, you need the 64-bit version of CentOS 7.

Here are [Docker's requirements](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/) for Ubuntu:

  * To install Docker CE, you need the 64-bit version of one of these Ubuntu versions:
    * Zesty 17.04
    * Xenial 16.04 (LTS)
    * Trusty 14.04 (LTS)

<div class='callout callout--neutral'>
  <p>Looking to skip the server installation and maintenance? Then check out our <a href="/gitkraken-client/stand-alone/">Serverless</a> solution.</p>
</div>




