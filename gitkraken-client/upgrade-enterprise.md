---

title: Upgrade
description:
taxonomy:
    category: gitkraken-client

---


The upgrade procedure is the same whether you are running GitKraken Self-Hosted on CentOS, Ubuntu, or RHEL7.

***

If you are upgrading to version 3.4.0, please [jump](#upgrade-to-v3.4.0) to the instructions at the bottom of this page.

<a id="upgrade-enterprise-server"></a>

## Upgrade Enterprise Server

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

**Note**: If upgrading in CentOS or RHEL7, you may need to specify the full path to the docker-compose installation.  The following commands should allow you to run the docker-compose command successfully:

```
sudo systemctl start docker.service
sudo /usr/local/bin/docker-compose up
```

<a id="upgrade-enterprise-clients"></a>

## Upgrade Enterprise Clients
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
<img src='/img/documentation/enterprise/license-settings.png' srcset='/img/documentation/enterprise/license-settings@2x.png 2x' class='img-bordered img-responsive center'>

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

<a id="upgrade-to-v3.4.0"></a>

## Upgrade to v3.4.0

<a id="migration-checklist"></a>

### Migration Checklist

* Go into GitKraken Self-Hosted admin page, navigate to the Server Config tab, and write down the listed URL.

* If you have deployed your own Mongo database and are not using the provided mongo container, you will need to provide GitKraken Self-Hosted an additional database. We suggest naming this database license or gk-license . It is ok for this database to exist on your existing mongo servers that are hosting the current GitKraken Self-Hosted database. This database is in addition to the database that GitKraken Self-Hosted currently consumes.

* Keep your old `docker-compose.yml` handy, it will be used for reference.

<a id="first-steps"></a>

### First Steps

<span>1.</span> Go to the folder where the previous installation of GitKraken Self-Hosted resides (the folder that contains the `docker-compose.yml`).

<span>2.</span> Take down the current instance of GitKraken Self-Hosted.
```
sudo docker-compose down
```

<span>3.</span> Back up the `docker-compose.yml` file.

<span>4.</span> Extract `GitKrakenEnterpriseServer.zip` in the folder you installed GitKraken Self-Hosted.  This should overwrite your current `docker-compose.yml` file.

<a id="important-changes-to-docker-compose"></a>

### Important Changes to docker-compose.yml

We have changed our image/container structure. The mapping from pre-3.4.0 to 3.4.0 is 1 to 1:

* `gk-enterprise` becomes `gk-enterprise-controller`

* `gk-api` becomes `gk-services`

<a id="migrating-gk-enterprise-to-gk-enterprise-controller"></a>

#### Migrating `gk-enterprise` to `gk-enterprise-controller`

Assuming the `gk-enterprise` service looks like this in the pre-3.4.0 `docker-compose.yml`:

```yml
gk-enterprise:
  image: docker.axosoft.com/gk-enterprise:release volumes:
    - ./gk-data/release:/enterprise/release
    - gk-config-data:/enterprise/config ports:
    - "3000:3000"
  links:
    - gk-api
  depends_on:
    - gk-api
  environment:
    - GITKRAKEN_API_URL=http://gk-api:3100
```

Then `gk-enterprise-controller` service should look like this in the 3.4.0 `docker-compose.yml`:

```yml
gk-enterprise-controller:
  image: gk-enterprise-controller:dev restart: always
  ports:
    - "3000:3000"
  volumes:
    - ./gk-data/release:/controller/release
  depends_on:
    - gk-mongo
  environment:
  GITKRAKEN_ENTERPRISE_URL: http://localhost:3000 GITKRAKEN_KAFKA_URL: gk-zookeeper:2181
```
**Volume Changes**

<table class='table table--bordered table--volumes'>
    <thead>
        <tr>
            <th>Old <code>docker-compose.yml</code> (<code>gk-enterprise</code>)</th>
            <th>New <code>docker-compose.yml</code> (<code>gk-enterprise-controller</code>)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>./gk-data/release:/enterprise/release</code></td>
            <td><code>./gk-data/release:/controller/release</code></td>
        </tr>
        <tr>
            <td><code>gk-config-data</code></td>
            <td>unused in 3.4.0</td>
        </tr>
    </tbody>
</table>

Take note that we've changed the container-side (right of `:`) location of the release volume. Your installation may have a different host-side (left of `:`) location than `./gk-data/release` than our example, but make sure that the container-side now points to `/controller/release`. Also keep in mind that `gk-config-data` is no longer used in
`gk-enterprise-controller`, but is still used by `gk-services`, so make sure it stays in the volume list at the end of the `docker-compose.yml` file.

**Environment Changes**

Take note of the environment section in `gk-enterprise-controller`. We have changed environment variables.

* We no longer use `GITKRAKEN_API_URL` in `gk-enterprise-controller`.

* Please update the `GITKRAKEN_ENTERPRISE_URL` to be the url that you retrieved from the admin site in the Migration Checklist

* We have added `GITKRAKEN_KAFKA_URL`. The default setting should be correct. Please see documentation in `docker-compose.yml` for further details.

<a id="migrating-gk-api-to-gk-services"></a>

### Migrating `gk-api` to `gk-services`

Assuming the `gk-api` services looks like this in the pre-3.4.0 `docker-compose.yml`:

```yml
gk-api:
  image: docker.axosoft.com/gk-api:release-enterprise
  volumes:
    - gk-config-data:/api/lib/config
  links:
    - gk-mongo
  depends_on:
    - gk-mongo
  environment:
    - GITKRAKEN_MONGO_URL=mongodb://gk-mongo:27017/api
```

Then `gk-services` service should look like this in the 3.4.0 `docker-compose.yml`:

```yml
gk-services:
  image: gk-services:dev restart: always
  volumes:
    - gk-config-data:/gk-services/services/gk-api/config
  ports:
    - "3100"
    - "3111"
  depends_on:
    - gk-mongo
    - gk-zookeeper
  environment:
    GITKRAKEN_ENTERPRISE_URL: http://localhost:3000
    GITKRAKEN_ENTERPRISE_INTERNAL_URL: http://gk-enterprise-controller:3000
    GITKRAKEN_KAFKA_URL: gk-zookeeper:2181
    GITKRAKEN_MONGO_URL: mongodb://gk-mongo:27017/api
    GITKRAKEN_MONGO_LICENSE_URL: mongodb://gk-mongo:27017/license
```

**Volume Changes**

<table class='table table--bordered table--volumes'>
    <thead>
        <tr>
            <th>Old <code>docker-compose.yml</code> (<code>gk-api</code>)</th>
            <th>New <code>docker-compose.yml</code> (<code>gk-services</code>)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>gk-config-data:/api/lib/config</code></td>
            <td><code>gk-config-data:/gk-services/services/gk-api/config</code></td>
        </tr>
    </tbody>
</table>

Take note that we've changed the container-side (right of `:`) location of the config volume. Make sure that the container- side now points to `/gk-services/services/gk-api/config`.

Take note of the environment section, as well. We have kept the `GITKRAKEN_MONGO_URL` environment variable, but we have added 3 new environment variables.

* Please update the `GITKRAKEN_ENTERPRISE_URL` to be the url that you retrieved from the admin site in the Migration Checklist

* For most cases the `GITKRAKEN_ENTERPRISE_INTERNAL_URL` should be left alone. See the `docker-compose.yml` provided by 3.4.0 for more information about this variable.

* `GITKRAKEN_MONGO_LICENSE_URL` should remain as it is defined unless a standalone mongo server has been configured. If a standalone mongo server has been configured, the value should be set to the connection string to the new database on that server that was discussed above in the Migration Checklist

* We have added `GITKRAKEN_KAFKA_URL`. The default setting should be correct. Please see documentation in `docker-compose.yml` for further details.

<a id="stand-up-gitkraken-enterprise-v3.4.0"></a>

### Stand up GitKraken Self-Hosted v3.4.0

1. LoadtheimagesintoDocker:
```
sudo sh loadImages.sh
```

2. In the same folder containing the `docker-compose.yml` file, run the following command:
```
sudo docker-compose up
```

<a id="migrating-to-a-super-user"></a>

### Migrating to a Super User

* Login as the current owner to create the new super user.

GitKraken Self-Hosted has added a new super user to manage the license. This super user replaces the original owner as the new owner of the license. When the original owner first logs into the new GitKraken Self-Hosted Account Site, they will be prompted to create a super user password. The owner will be downgraded to an admin as to retain some administrative capabilities over the license.

Before a super user is created, the config cannot be updated by anyone, including the owner. It is important that the owner log into the account site as soon as possible to facilitate the creation of the super user. To login as the super user, simply visit the login page and click the link to "Login as Super User".

The super user does not consume a license, cannot log into the GitKraken client, and cannot be changed or viewed from the account site user management page.

If you forget the super user password, you can restart GitKraken Self-Hosted with a special flag `SUPER_USER_RESET`. To find out more about resetting the super user, see the `SETUP_README.md`.
