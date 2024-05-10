---

title: How to Install GitKraken Desktop 
description: Learn how to install GitKraken Desktop on Windows, Mac, and Linux.
taxonomy:
    category: gitkraken-client

---

There are three steps to success with GitKraken Desktop. That's it!

1. [Download](https://gitkraken.com/download) GitKraken Desktop
2. Install GitKraken Desktop
3. Use GitKraken Desktop

No Git tools are required for GitKraken Desktop, so once you’ve run the installer, you can open the app and get going.

If you want to utilize additional features such as the terminal or LFS, <a href='https://git-scm.com/' target="_blank">download git-scm </a>.


Below are platform-specific instructions and details on minimum requirements.

<div class='callout callout--basic'>
    <p>Looking for <em>GitKraken On-Premise Self-Hosted</em> installation instructions? Then please start in with our <a href="/enterprise/system-requirements">On-Premise System Requirements</a> page. </p>
</div>

***
## Windows (.exe file)
* **System requirements:** Windows 10+
    * [Download (64-bit)](https://gitkraken.com/download/windows64)

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/obIK_732_9M?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>

### Install Instructions
Double-click the downloaded executable file. You will see a splash screen while GitKraken Desktop is insalled, and then the application will automatically start.

### Windows Data Location
GitKraken Desktop data is stored with your home profile in `C:\\Users\\{user}\\AppData\\Roaming` in the `.gitkraken` folder.

***
## Mac OS (.dmg file)
* **System requirements:**
    * Intel: macOS 10.15+
    * Apple Silicon: macOS 11+
* [Download](https://gitkraken.com/download/mac)

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/22HD1ZnNytk?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>

### Install Instructions
Double click the downloaded DMG file and when prompted, drag and drop the GitKraken icon to your Applications folder.

<img src="/wp-content/uploads/mac-install.png" class="img-responsive center img-bordered">

### Mac OS Data Location
GitKraken Desktop data is stored in `/Users/{user}/.gitkraken` == `~/.gitkraken`.

***
## Linux (.deb, .rpm, and .tar.gz files)
* **.deb system requirements:** Ubuntu 18.04 LTS or later
* **.rpm system requirements:** RHEL 7+, CentOS 7+, or Fedora 34+

<div class='callout callout--warning'>
    <p>Note 📝 - GitKraken Desktop currently supports Ubuntu 18.04 LTS+, RHEL 7+, CentOS 7+, and Fedora 34+. While GitKraken Desktop may be able to be installed on other Linux distributions, we cannot guarantee that it will work as expected.</p>
</div>

<div class='embed-container embed-container--16-9'>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/Cx4aQzlMSw4?ecver=1" frameborder="0" allowfullscreen></iframe>
</div>

### .deb
GitKraken Desktop has a simple package available for Debian based distributions.
```
wget https://release.gitkraken.com/linux/gitkraken-amd64.deb
sudo apt install ./gitkraken-amd64.deb
```
Or [download the file](https://gitkraken.com/download/linux-deb).

### .tar
```
wget https://release.gitkraken.com/linux/gitkraken-amd64.tar.gz
sudo tar -xvzf gitkraken-amd64.tar.gz
```
Or [download the file](https://gitkraken.com/download/linux-gzip).

### .rpm
```
wget https://release.gitkraken.com/linux/gitkraken-amd64.rpm
sudo dnf install ./gitkraken-amd64.rpm
```
Or [download the file](https://gitkraken.com/download/linux-rpm).

Note: for older distros that do not have ```dnf```, you should use ```yum``` instead.



### Snap

Snap is an easy-to-install package for Linux distributions (supported versions above). Get it from the snap store or [Snapcraft.io](https://snapcraft.io/gitkraken).

### Linux Data Location
GitKraken Desktop data is stored in `/home/{user}/.gitkraken` == `~/.gitkraken`.

### WSL
If you're attempting to use GitKraken Desktop within Windows Subsystem for Linux (WSL), visit our page on <a href="https://help.gitkraken.com/gitkraken-client/windows-subsystem-for-linux/">How to use GitKraken Desktop with WSL</a> for additional details.

## Run GitKraken Desktop

Upon installation, some Linux distros do not automatically create shortcuts to the app.

To run GitKraken Desktop manually, open the terminal and type `gitkraken` to start the app.

