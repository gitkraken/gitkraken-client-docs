---

title: Upgrade GitKraken Self-Hosted Server
description: Learn how to upgrade your GitKraken Self-Hosted Server instance
taxonomy:
    category: gitkraken-client

---


The upgrade procedure is the same whether you are running GitKraken Self-Hosted on CentOS, Ubuntu, or RHEL7.

***

<a id="upgrade-enterprise-server"></a>

## Upgrade Self-Hosted Server

<span>1.</span> Go to the folder where the previous installation of GitKraken Self-Hosted resides
(the folder that contains the _docker-compose.yml_).

<span>2.</span> Take down the current instance of GitKraken Self-Hosted:
```
sudo docker-compose down
```

<span>3.</span> Back up the _docker-compose.yml_ file.

<span>4.</span> Extract _GitKrakenEnterpriseServer.zip_ in the folder you installed GitKraken Self-Hosted.
This should overwrite your current _docker-compose.yml_ file.

<span>5.</span> Make sure to address any configuration differences between the new _docker-compose.yml_ and the
old _docker-compose.yml_. This includes:

  * Any public facing port changes.
  * Location of volumes on the host computer.
  * Any environment variable changes.

<span>6.</span> For setups that do not utilize docker-compose, make note of the image names and tags,
and ensure that your swarm manager addresses those changes (an example would be Nomad
setups).

<span>7.</span> Load the images into Docker:
```
sudo sh loadImages.sh
```

<span>8.</span> In the same folder containing the _docker-compose.yml_ file, run the following command:
```
sudo docker-compose up
```

**Note**: If server configuration is lost after upgrading, verify that `docker-compose up` was ran from the same directory as before.

**Note**: If upgrading in CentOS or RHEL7, you may need to specify the full path to the docker-compose installation.  The following commands should allow you to run the docker-compose command successfully:

```
sudo systemctl start docker.service
sudo /usr/local/bin/docker-compose up
```

<a id="upgrade-enterprise-clients"></a>

## Upgrade Self-Hosted Clients
<span>1.</span> Open your _docker-compose.yml_ file where you installed GitKraken Self-Hosted.

<span>2.</span> Locate the `gk-enterprise-controller` service. Under volumes, there should be a volume:
```
-./gk-data/release:/controller/release # The volume where GitKraken Self-Hosted clients go.
```

<span>3.</span> We can divide this line into 2 distinct parts by separating at the ":".
The first half in our example is _./gk-data/release_ and the second half is _/enterprise/release_.
The first half represents where the clients are located on your host machine, and it may be different
than this example.

<span>4.</span> Navigate to the folder where the clients are stored. Extract _release.zip_ and overwrite all data in that
folder at the top level.

<span>5.</span> When you have completed extracting the zip, in our example, our release folder will have the following shape:
```
./gk-data/
   └── release/
       ├── linux/
       ├── darwin/
       ├── win32/
       └── win64/
```

<span>6.</span> Users of GitKraken Self-Hosted should now start receiving the latest client.

<a id="update-license"></a>

## Update License

If you need to update your GitKraken Self-Hosted license, you will first need to copy the license.dat file over to your GitKraken Self-Hosted server.  Then, select the new license by going to the License tab on your Enterprise site.  From here you can browse to the new license file:
<img src='/wp-content/uploads/license-settings.png' srcset='/wp-content/uploads/license-settings@2x.png 2x' class='img-bordered img-responsive center'>

<a id="reset-the-super-user-password"></a>

### Reset the Super User Password

Follow these steps to reset the Super User password.

Shutdown GitKraken Self-Hosted by running:
```
sudo docker-compose down
```

Set the `gk-services` environment variable `SUPER_USER_RESET` to 1 in the `docker-compose.yml` file.
```yaml
environment:
  SUPER_USER_RESET: 1
```

Restart GitKraken Self-Hosted by running:
```
sudo docker-compose up
```

On the account site, visit `/reset/super-user` and provide the new password.

After resetting the super user, verify that you can login as the super user.  

Once login is verified, you need to restart without the reset flag.  Shutdown GitKraken Self-Hosted by running:
```
sudo docker-compose down
```

Delete the `SUPER_USER_RESET` environment variable from `gk-services` in the `docker-compose.yml`.

Restart GitKraken Self-Hosted by running:
```
sudo docker-compose up
```
