---

title: Install
description:
taxonomy:
    category: gitkraken-client

---

GitKraken Self-Hosted runs on a Linux virtual machine (CentOS, Ubuntu, or RHEL7) inside Docker containers, so before we can boldy go where no Kraken has gone before, we'll have to install Docker.

[Jump](#install_centos) to CentOS</br>
[Jump](#install_ubuntu) to Ubuntu</br>
[Jump](#install_rhel7) to RedHat Enterprise Linux 7</br>

***

 <a id="install_centos"></a> 

##Install Docker CE on CentOS

These instructions can also be found on [Docker's documentation site](https://docs.docker.com/engine/installation/linux/centos/#install-docker).
### With internet access

[comment]: <> (Enclosing list number with <span></span> allows list to be held and code snippet to be copied)

<span>1.</span> Install required packages:
```
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```

<span>2.</span> Use the following command to set up the stable repository:<br/>
```
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

<span>3.</span> Update the yum package index:
```
sudo yum makecache fast
```

<span>4.</span> Install the latest version of Docker:
```
sudo yum install docker-ce
```

<span>5.</span> Edit _/etc/docker/daemon.json_. If it does not yet exist, create it:
```
{
"storage-driver": "devicemapper"
}
```

<span>6.</span> Start Docker:
```
sudo systemctl start docker
```

<span>7.</span> Switch to root user:
```
sudo su
```

<span>8.</span> Download Docker Compose:
```
curl -L https://github.com/docker/compose/releases/download/1.14.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
```

<span>9.</span> Apply executable permissions:
```
sudo chmod +x /usr/local/bin/docker-compose
```

<span>10.</span> Install GitKraken Self-Hosted - [jump](#install_enterprise) to Installation section.

### Without internet access

<span>1.</span> Download Docker CE and Docker Compose packages from a machine with internet access.

  * [Docker CE for CentOS](https://download.docker.com/linux/centos/7/x86_64/stable/Packages/)  (both the docker-ceselinux and the docker-ce of the same version (e.g. 17.03.1))
  * [Docker Compose](https://github.com/docker/compose/releases/download/1.14.0/docker-compose-Linux-x86_64)

<span>2.</span> Get the 3 files over to the host server where Docker will be installed.

<span>3.</span> Install Docker (change the path to where you copied the files, and the package names appropriately):
```
sudo yum install /path/to/docker-ce-selinux-package.rpm
sudo yum install /path/to/docker-ce-package.rpm
```

<span>4.</span> Copy and rename the Docker Compose file to _/usr/local/bin/docker-compose_:
```
sudo mv docker-compose-Linux-x86_64 /usr/local/bin/docker-compose
```

<span>5.</span> Change access permission for _docker-compose_:
```
chmod +x /usr/local/bin/docker-compose
```

<span>6.</span> Edit _/etc/docker/daemon.json_. If it does not yet exist, create it:
```
{
"storage-driver": "devicemapper"
}
```

<span>7.</span> Start Docker:
```
sudo systemctl start docker
```

<span>8.</span> Install GitKraken Self-Hosted - [jump](#install_enterprise) to Installation section.

<a id="install_ubuntu"></a>

## Install Docker CE on Ubuntu

These instructions can also be found on [Docker's documentation site](https://docs.docker.com/engine/installation/linux/ubuntu/#install-docker).

### With internet access
<span>1.</span> Install packages to allow apt over HTTPS:
```
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
```

<span>2.</span> Add Docker's GPG key:
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
   You can verify the key with:
   ```
   sudo apt-key fingerprint 0EBFCD88
   ```

<span>3.</span> Set up the stable repository:
```
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu
$(lsb_release -cs) stable"
```

<span>4.</span> Update apt package index:
```
sudo apt-get update
```

<span>5.</span> Install Docker:
```
sudo apt-get install docker-ce
```

<span>6.</span> Switch to root user:
```
sudo su
```

<span>7.</span> Download Docker Compose:
```
curl -L https://github.com/docker/compose/releases/download/1.14.0/docker-compose-
`uname -s`-`uname -m` > /usr/local/bin/docker-compose
```

<span>8.</span> Apply executable permissions:
```
sudo chmod +x /usr/local/bin/docker-compose
```

<span>9.</span> Install GitKraken Self-Hosted - [jump](#install_enterprise) to Installation section.

### Without internet access

<span>1.</span> Download Docker CE package from a machine with internet access.

  * [Docker CE for Ubuntu](https://download.docker.com/linux/ubuntu/dists/) choose your Ubuntu version, browse to pool/stable, and choose your architecture.

   You can check your version using:
   ```
   lsb_release -a
   ```

<span>2.</span> Download Docker Compose package from a machine with internet access.
  * [Docker Compose](https://github.com/docker/compose/releases/download/1.14.0/docker-compose-Linux-x86_64)

<span>3.</span> Get the 2 files over to the host server where Docker will be installed.

<span>4.</span> Install Docker (change the path to where you copied the files, and change the package names appropriately):
```
sudo dpkg -i /path/to/package.deb`
(e.g. `sudo dpkg -i docker-ce_17.06.0-ce-0-ubuntu_amd64.deb`)
```

<span>5.</span> Move Docker Compose file and rename it:
```
sudo mv docker-compose-Linux-x86_64 /usr/local/bin/docker-compose
```

<span>6.</span> Apply executable permissions:
```
sudo chmod +x /usr/local/bin/docker-compose
```

<a id="install_rhel7"></a> 

## Install Docker CE on RHEL7

### With internet access

<span>1.</span> Install required packages:
```
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```

<span>2.</span> Use the following command to set up the stable repository:
```
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

<span>3.</span> Update the yum package index:
```
sudo yum makecache fast
```

<span>4.</span> Install the latest version of Docker:
```
sudo yum install --setopt=obsoletes=0 docker-ce-17.03.2.ce-1.el7.centos.x86_64 docker-ce-selinux-17.03.2.ce-1.el7.centos.noarch
```
  * Note: If you would like to install the latest version of Docker CE, you can run the following command to get the latest version:
```
yum list docker-ce --showduplicates | sort -r
```
Insert the desired Docker CE version into the install command by replacing that portion of the string for the Docker CE version and the selinux version.

<span>5.</span> Edit _/etc/docker/daemon.json_. If it does not yet exist, create it:
```
{
"storage-driver": "devicemapper"
}
```

<span>6.</span> Start Docker:
```
sudo systemctl start docker
```

<span>7.</span> Switch to root user:
```
sudo su
```

<span>8.</span> Download Docker Compose:
```
curl -L https://github.com/docker/compose/releases/download/1.14.0/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
```

<span>9.</span> Apply executable permissions:
```
sudo chmod +x /usr/local/bin/docker-compose
```

<span>10.</span> Install GitKraken Self-Hosted - [jump](#install_enterprise) to Installation section.

### Without internet access

<span>1.</span> Download Docker CE and Docker Compose packages from a machine with internet access.

  * [Docker CE for CentOS](https://download.docker.com/linux/centos/7/x86_64/stable/Packages/)  (both the docker-ceselinux and the docker-ce of the same version (e.g. 17.03.1))
  * [Docker Compose](https://github.com/docker/compose/releases/download/1.14.0/docker-compose-Linux-x86_64)

<span>2.</span> Get the 3 files over to the host server where Docker will be installed.

<span>3.</span> Install Docker (change the path to where you copied the files, and the package names appropriately):
```
sudo yum install /path/to/docker-ce-selinux-package.rpm
sudo yum install /path/to/docker-ce-package.rpm
```

<span>4.</span> Copy and rename the Docker Compose file to _/usr/local/bin/docker-compose_:
```
sudo mv docker-compose-Linux-x86_64 /usr/local/bin/docker-compose
```

<span>5.</span> Change access permission for _docker-compose_:
```
chmod +x /usr/local/bin/docker-compose
```

<span>6.</span> Edit _/etc/docker/daemon.json_. If it does not yet exist, create it:
```
{
"storage-driver": "devicemapper"
}
```

<span>7.</span> Start Docker:
```
sudo systemctl start docker
```

<span>8.</span> Install GitKraken Self-Hosted - [jump](#install_enterprise) to Installation section.

<a id="install_enterprise"></a>

##  Install GitKraken Self-Hosted

<span>1.</span> Extract _GitKrakenEnterpriseServer.zip_ in a folder of your choosing
(all commands in the following instructions will be performed in that folder).

<span>2.</span> Load the images into Docker:
```
sudo sh loadImages.sh
```

<span>3.</span> Configure what port GitKraken Self-Hosted should run on the host server.
By default GitKraken Self-Hosted server will run on port 3000.

  You can change the port by opening up the _docker-compose.yml_ file and making a few modifications.  
  First, find the `ports` section under `gk-enterprise-controller`:
  ```yaml
    ports:
      "3000:3000"
  ```

  Modify the first `3000` to the desired port
  For example, to use port 80 change it to:

  ```yml
    ports:
      "80:3000"
  ```

  Then update the `GITKRAKEN_ENTERPRISE_URL` environment variable to use the desired port.  Again, for port 80 it would look like:
  ```yaml
    environment:
        GITKRAKEN_ENTERPRISE_URL: http://localhost:80
  ```

  Finally, find the `GITKRAKEN_ENTERPRISE_URL` environment variable in the `gk-services` section and modify the port.  For port 80, this would look like:
  ```yaml
    environment:
        GITKRAKEN_ENTERPRISE_URL: http://localhost:80
  ```

<span>4.</span> Configure where GitKraken client releases are stored on your host server.
By default the releases folder is set to _./gk-data/release_. You can change the location by opening up
the _docker-compose.yml_ file and finding the section under `gk-enterprise-controller`:
```
volumes:
 ./gk-data/release:/controller/release # The volume where GitKraken Self-Hosted clients go.
```
and modifying _./gk-data/release_ to point to another directory on your host server.

<span>5.</span> Create the folder specified in the above step on your host server.

<span>6.</span> Extract _release.zip_ in the folder you created on your host server
(releases will always be extracted in this folder).

<span>7.</span> In the same folder containing the _docker-compose.yml_ file, run the following command:
```
sudo docker-compose up
```
  * To run this command in the background, use `docker-compose up -d` instead.
  * Note: If installing in CentOS or RHEL7, you may need to specify the full path to the docker-compose installation.  The following commands should allow you to run the docker-compose command successfully:
```
sudo systemctl start docker.service
sudo /usr/local/bin/docker-compose up
```

<span>8.</span> Navigate to http://localhost:3000 and complete the setup
(the port in the URL should match the port from step 3, if it was changed).
