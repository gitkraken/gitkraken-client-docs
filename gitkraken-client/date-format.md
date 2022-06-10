---

title: Date Format
description: Learn how to set up your system's date/time format into GitKraken Client.
taxonomy:
    category: gitkraken-client

---

***
## Mac and Linux
GitKraken Client will automatically adopt your system's date format if you are using Mac or Linux. This is based on your operating system's language.

In some cases on Linux, defining the `LANG` variable will not be enough for GitKraken Client to detect the correct language setting. You will instead need to define the `LANGUAGE` variable.

***
## Windows
If GitKraken Client is not recognizing your Windows system's date format, please verify whether the correct language package is installed on your machine.

First, check that your system's date, time, or number formats is set to `Match Windows display language` by navigating to <kbd><strong>Control Panel > Change date, time, or number formats > Format</strong></kbd>:


<img src="/wp-content/uploads/formatSetting.png" srcset="/wp-content/uploads/formatSetting@2x.png 2x" class="img-responsive center img-bordered">

Once this is configured, navigate to <kbd><strong>Settings > Time & language</strong></kbd>:

<img src="/wp-content/uploads/time-language.png" srcset="/wp-content/uploads/time-language@2x.png 2x" class="img-responsive center img-bordered">

Now select `Region & language`:

<img src="/wp-content/uploads/region-language.png" srcset="/wp-content/uploads/region-language@2x.png 2x" class="img-responsive center img-bordered">

Next, select `Add a language` and select the language you wish your system to be configured to:

<img src="/wp-content/uploads/add-language.png" srcset="/wp-content/uploads/add-language@2x.png 2x" class="img-responsive center img-bordered">

Once you have picked your language, select it under the `Region & language` window and choose _Options_.

On the next screen, click `Download` under _Download language pack_. When the download finishes, navigate back to the `Region & language` window and select the _Select as default_ option.

<img src="/wp-content/uploads/set-language.png" srcset="/wp-content/uploads/set-language@2x.png 2x" class="img-responsive center img-bordered">

GitKraken Client will now use your system's date format 🎉
