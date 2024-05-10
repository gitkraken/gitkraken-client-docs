---

title: GitKraken Desktop and Windows Subsystem for Linux (WSL)
description: How to use GitKraken Desktop with Windows Subsystem for Linux (WSL)
taxonomy:
    category: gitkraken-client

---

Learn all about GitKraken Desktop and WSL 2.
## What is WSL/WSL 2?

<a href="https://learn.microsoft.com/en-us/windows/wsl/about" target="_blank">Windows Subsystem for Linux (WSL)</a> lets developers install a Linux distribution and use Linux applications, utilities, and Bash command-line tools directly on Windows. <a href="https://learn.microsoft.com/en-us/windows/wsl/compare-versions" target="_blank">WSL 2</a> utilizes an actual Linux kernel inside a managed virtual machine (VM) to provide improved performance and full system call capability, and is now the default WSL version. Microsoft notes that WSL 2 lacks performance across OS file systems however, and this issue can be addressed by storing your project files on the same operating system as the tools you are running to work on the project.

Microsoft also introduced <a href="https://learn.microsoft.com/en-us/windows/wsl/tutorials/gui-apps" target="_blank">Windows Subsystem for Linux GUI (WSLg)</a>, a feature aimed to provide the ability to run Linux GUI applications in a Linux/WSL 2 environment. Using WSLg also better enables Linux GUI applications like the Linux version of GitKraken Desktop to feel native and natural to use on Windows by integrating them closely into the Windows desktop experience when running within WSL 2.

## How to use GitKraken Desktop with WSL 2

<img src="/wp-content/uploads/wsl-full-screen.png" srcset="/wp-content/uploads/wsl-full-screen@2x.png" class="img-bordered img-responsive center">

GitKraken Desktop can work with repos stored on your WSL 2 file system when installed within the WSL 2 environment and using WSL’s built-in display server functionality, <a href="https://learn.microsoft.com/en-us/windows/wsl/tutorials/gui-apps" target="_blank">WSLg</a>, for GUI support. The Linux version of GitKraken Desktop has been updated to fix common issues when operating GitKraken within WSL 2, and includes settings to [set preferences](#preferences-for-gitkraken-on-wsl-2) for where to open web links and files opened by GitKraken running within WSL 2.

<div class='callout callout--warning'>
    <p><strong>Note:</strong> GitKraken Desktop does not currently support cross file system access for repos stored on both Windows and WSL. GitKraken Desktop should be installed on the operating system where your repos are stored for the best experience. Opening repos across file systems may severly degrade performance and features may not work as intended.</p>
</div>

GitKraken Desktop will also detect where a repo is stored and notify the end user via pop-up. This allows for quick management of GitKraken Desktop when working with both Windows and WSL repos. For more information, see the section on [Working Across File Systems](#working-across-file-systems-in-wsl-2).

There are 4 steps to start using GitKraken Desktop with your WSL repos:
1. Confirm the latest version of WSL 2 is installed that supports WSLg
2. Download the latest Linux version of GitKraken Desktop
3. Install GitKraken Desktop on your WSL 2 environment
4. Use GitKraken Desktop

No Git tools are required to use GitKraken Desktop, but if you want to utilize additional features such as the terminal or LFS, you will need to have Git installed within your WSL distribution. Git comes already installed with most of the Windows Subsystem for Linux distributions, however, if you want to manually update or install the latest version, visit the <a href="https://git-scm.com/download/linux" target="_blank">Git installation instructions for Linux</a>.

Below are instructions and minimum requirements to run GitKraken Desktop within WSL 2.
***
## WSL 2/WSLg Requirements

- Windows 11 or Windows 10 build 19044 or later
- WSL 2 distribution
- GitKraken Desktop version 9.1.0+ for Linux

***

## Install or Update WSL 2 with WSLg Support

GitKraken Desktop will only work with WSL 2 on Windows 11 or Windows 10 build 19044 or later, which includes WSLg for GUI support.

If you already have WSL installed with a Linux distro, run the following command from PowerShell or Windows Command Prompt to update to the latest version of WSL. Make sure to open as administrator if you use Windows Command Prompt.
```
wsl --update 
```
If you need to install WSL with the default Ubuntu distribution of Linux, simply run the following command from PowerShell or Windows Command Prompt opened as administrator and reboot if prompted.
```
wsl --install -d ubuntu
```
After reboot the installation will continue. You'll be asked to enter a username and password within the Linux terminal. These will be your Linux credentials.

WSLg is automatically included as part of the update and initial WSL setup, so you are ready to install GitKraken Desktop.
***
## Download and Install GitKraken Desktop on WSL 2

To install GitKraken within WSL, please follow our instructions for <a href="https://help.gitkraken.com/gitkraken-client/how-to-install/#linux-deb-rpm-and-tar-gz-files" target="_blank">installing GitKraken Desktop on Linux</a> and remember to open your Linux terminal from Windows as administrator.

If you are using Ubuntu as your Linux distribution, you will run the following commands within the Linux terminal to download and install GitKraken Desktop within WSL:
```
wget https://release.gitkraken.com/linux/gitkraken-amd64.deb
sudo apt install ./gitkraken-amd64.deb
```
If the installation does not complete because of missing packages, you may need to run the following command before attempting to install again. 
```
sudo apt --fix-broken install
```
You’re all set! You should now be able to open GitKraken Desktop and work with repos stored within WSL.
To open GitKraken Desktop within WSL, you can always run the following command from your Linux terminal:
```
gitkraken
```
Note: If you choose to install GitKraken Desktop from the .tar.gz file, gitkraken must be installed on `PATH` for this command to work
***
## Preferences for GitKraken on WSL 2

When running GitKraken Desktop within WSL 2, additional preferences are available to tell GitKraken where you'd like to open URLs and files opened by GitKraken. You'll see these settings in `Preferences` > `General` when running within WSL 2.

<img src="/wp-content/uploads/wsl-host-settings.png" srcset="/wp-content/uploads/wsl-host-settings@2x.png" class="img-bordered img-responsive center">

By default, URLs will open in your Windows default browser and other files opened by GitKraken will attempt to open on the host distribution.

***
## Known Issues with WSL 2

- <a href="https://github.com/microsoft/wslg/issues/388" target="_blank">HiDPI Displays cause WSLg to inconsistently scale the UI</a>
- <a href="https://github.com/microsoft/wslg/issues/727" target="_blank">Window snapping does not work with WSLg</a>

***
## Troubleshooting WSL 2

If GitKraken loads with a black screen, or other graphical errors persist, try reopening GitKraken Desktop as administrator or update your graphics card drivers.

If graphical errors are still present, you can disable GPU hardware acceleration by running GitKraken Desktop with the following command:

```
gitkraken --disable-gpu
```

If you are receiving a `NET:ERR_CERT_AUTHORITY_INVALID` error when attempting to login, try running GitKraken Desktop with the following command:

```
gitkraken --ignore-certificate-errors
```

For other errors, you may need to restart WSL. You can run the following command from PowerShell or Windows Command Prompt running as administrator:
```
wsl --shutdown
```
Then, reopen your Linux distribution or GitKraken Desktop as administrator.

***
## Working Across File Systems in WSL 2

Microsoft recommends against working across operating systems when using WSL 2, and GitKraken does not currently support cross file system access of repos. To get around this limitation, you can install a seperate GitKraken Desktop on both the Windows side and WSL Linux side. Then GitKraken will notify you when opening a repo across operating systems and allow you to directly open the repo in the recommended installation of GitKraken. When attempting to open a new repo that is on WSL 2 from GitKraken installed on Windows, or Windows from GitKraken installed on WSL 2, the following message will appear:

<img src="/wp-content/uploads/wsl-toast.png" srcset="/wp-content/uploads/wsl-toast@2x.png" class="img-bordered img-responsive center">

You will be asked to choose an option to proceed:
- `Open Help Center` will take you to this page in your browser for information on how to set up GitKraken within WSL 2.

- `Open with GitKraken on Ubuntu/Windows` will open the repository you're attempting to open in the recommended version of GitKraken if installed in the operating system where the repository is stored. This will work for both Windows and WSL 2 repositories that are being accessed from a different operating system.

- `Open Anyway` will open the repository. Features may behave in unintended ways, simply not function, and performance may be severely degraded when opening from a different operating system.

- Closing the message will cancel opening the repository

<div class='callout callout--warning'>
    <p><strong>Note:</strong> If you open a repository in WSL through a mapped network drive from Windows, GitKraken Desktop will not detect that the repository is being accessed across file systems and attempt to open normally. This may lead to unintended behavior and is not recommended.</p>
</div>