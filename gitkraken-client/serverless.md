---

title: GitKraken On-Premise Serverless
description: How to install and use GitKraken On-Premise Serverless.
taxonomy:
    category: gitkraken-client

---

GitKraken Client On-Premise Serverless (also known as *GitKraken Stand-Alone* or simply *GitKraken Serverless*) is built for teams and enterprises who work in a disconnected development environment. You get most of the same core <a href="https://www.gitkraken.com/git-client" target=_blank>GitKraken features</a>, along with these additional benefits:

- For use without internet
- No account creation required
- No server installation

<img src="/wp-content/uploads/standalone-glory.png" srcset="/wp-content/uploads/standalone-glory@2x.png 2x" class="img-responsive center img-bordered">

<div class='callout callout--basic'>
    <p>Looking to get started with GitKraken Serverless? Email <a href="mailto:sales@gitkraken.com" target=_blank>sales@gitkraken.com</a> for a trial key.</p>
</div>
---

## How to install GitKraken Serverless

There are 3 steps to installing GitKraken Serverless

1. <a href="https://www.gitkraken.com/download-on-premise-serverless" target=_blank>Download</a> GitKraken Serverless
2. Install GitKraken Serverless
3. Load `.dat` license file

### 1. Download GitKraken Serverless

The GitKraken Serverless Clients are available on our <a href="https://www.gitkraken.com/download-on-premise-serverless" target=_blank>downloads</a> page.

If you are unable to access this page, please contact your GitKraken administrator for GitKraken Serverless client downloads. There is a high probability they have made the files available in a different, internal location.


### 2. Install GitKraken Serverless

Once you download the client, double click the file to install the GitKraken Serverless Client on your machine. 

Below are platform-specific details on minimum requirements.

### Windows (.exe file)
* **System requirements:** Windows 10

#### Install Instructions
Double-click the downloaded executable file, and follow the installation instructions.

#### Data Location
GitKraken data is stored within your home profile in `C:\\Users\\{user}\\AppData\\Roaming` or `%APPDATA%\\.gitkraken` on older versions. No data is stored outside of the user's machine or remote services _(GitHub Enterprise, Bitbucket Server, etc)_.



***
### Mac OS (.dmg file)
* **System requirements:** Mac OS X 10.11+

#### Install Instructions
Double click the downloaded DMG file and when prompted, drag and drop the GitKraken icon to your Applications folder.

#### Data Location
GitKraken data is stored in `/Users/{user}/.gitkraken` == `~/.gitkraken`. No data is stored outside of user's machine or remote services _(GitHub Enterprise, Bitbucket Server, etc)_.

***
### Linux (.deb and .tar.gz files)
* **System requirements:** Ubuntu LTS 18.04 or later

#### .deb
GitKraken has a simple package available for Debian based distributions.
```
wget https://release.gitkraken.com/linux-standalone/gitkraken-amd64.deb
dpkg -i gitkraken-amd64.deb
```

#### .tar
```
wget https://release.gitkraken.com/linux-standalone/gitkraken-amd64.tar.gz
tar -xvzf gitkraken-amd64.tar.gz
```

#### Data Location
GitKraken data is stored in `/home/{user}/.gitkraken` == `~/.gitkraken`. No data is stored outside of user's machine or remote services _(GitHub Enterprise, Bitbucket Server, etc)_.

***

### 3. Load license file

When you first open GitKraken Stand-Alone Client, you will be prompted to load the `.dat` license file. 

<img src="/wp-content/uploads/license.png" class="img-responsive center img-bordered">

If do not have the license, please contact your GitKraken administrator. If you are the GitKraken administrator, yiou can find your license file on app.gitkraken.com. If you have an older account or you need assistance locating your license file, [contact us](https://help.gitkraken.com/gitkraken-client/contact-support/).

Once the license file is applied, you are ready to get crackin'!

<img src="/wp-content/uploads/standalone.png" srcset="/wp-content/uploads/standalone@2x.png 2x" class="img-responsive center img-bordered">

#### License.dat Location
You can also place your license file into specific directory locations for GitKraken to check. Here are all of the locations GitKraken Client will look:

**Linux/Mac:**

- `/usr/local/share/gitkraken`

- `/usr/share/gitkraken`

- directory above the `exe`

- directory of the `exe`

- `~/.gitkraken`

**Windows:**

- ``C:\ProgramData\GitKraken``

- directory above the `exe`

- directory of the `exe`

- ``%APPDATA%\.gitkraken``
