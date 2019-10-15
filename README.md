# aem-spa-experiments

Experimenting with Adobe Experience Manager and Single Page Apps

## See Also

- [42 — AEM SPA Editor](https://42.industrieit.com/pages/viewpage.action?spaceKey=Partners&title=AEM+SPA+Editor)
- [Adobe Experience Manager](https://helpx.adobe.com/support/experience-manager/6-5.html)
- [AEM Single Page Editor](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-spa-editor.html) — watch the video. (approx 1 hour)
- [AEM Author in Docker](https://hub.docker.com/r/pawangonnakuti/aem-author)
- [AEM Publish in Docker](https://hub.docker.com/r/pawangonnakuti/aem-publish)
- [SPA Walkthrough](https://helpx.adobe.com/experience-manager/6-5/sites/developing/using/spa-walkthrough.html)
- [AEM Example 'we retail journal'](https://github.com/adobe/aem-sample-we-retail-journal)
- [Maven Archetype for SPA Starter Kit](https://github.com/adobe/aem-spa-project-archetype)

## Run AEM (Authoring and Publishing Environments)

in `/config` create a file called `license.properties` with the following content:

```env
#Adobe Granite License Properties
#Fri May 03 09:28:09 AEST 2019
license.product.name=Adobe Experience Manager
license.customer.name=YOUR NAME GOES HERE
license.product.version=6.5.0
license.downloadID=YOUR LICENSE ID GOES HERE
```

```sh
docker-compose up -d
```

The first time you run these services they'll take a long time (> 5 minutes) to start.

## The services

- [Authoring: localhost:4502](https://localhost:4502)
- [Publishing: localhost:4503](https://localhost:4503)

You can log in to either with `admin` and `admin`

## Development

<!-- prettier-ignore -->
| branch | status | coverage | notes |
| ------ | ------ | -------- | ----- |
| `develop` |  |  | Work in progress |
| `master`  |  |  | Latest stable release |

### Prerequisites

- [NodeJS](https://nodejs.org) version 10.16.3 or better (I use [`nvm`](https://github.com/creationix/nvm) to manage Node versions — `brew install nvm`.)
- [Docker](https://www.docker.com) (Use [Docker for Mac](https://docs.docker.com/docker-for-mac/), not the homebrew version)
- [Java](https://www.java.com/en/download/) version 1.8 or better and be sure to set the `JAVA_HOME` environment variable.  To see if it's set check

      echo $JAVA_HOME

  If `JAVA_HOME` is not set then add it to your `~/.zsh_profile` (or whichever shell equivalent you are using)

      export JAVA_HOME=$(/usr/libexec/java_home)

- [Maven](https://maven.apache.org/) `brew install maven`
- [aem-spa-project-archetype](https://github.com/adobe/aem-spa-project-archetype)

  You'll need to `git clone` this to somewhere on your local machine, then `cd` into that directory and build it with

      mvn clean install archetype:update-local-catalog
      mvn archetype:crawl

  **Note**: the install process downloads a few GB of data very slowly from Adobe and can take a half an hour, or more, to complete.

### Building your first Single Page App

We are going to build a `react` app.

Create a new folder for your project

    mkdir spa-example
    cd spa-example

Then run the maven archetype.

    mvn archetype:generate \
     -DarchetypeCatalog=local \
     -DarchetypeGroupId=com.adobe.cq.spa.archetypes  \
     -DarchetypeArtifactId=aem-spa-project-archetype  \
     -DarchetypeVersion=1.1.0

The script will ask you some questions. For the `groupId` use `spa-example` and for the `artifactId` use `spa-example.example`.

The resulting shell of a react app can be found in `spa-example.example/react-app/`

Now, assuming you are running your local versions of AEM Author and Publisher (as per above)

1. Browse to [`localhost:4502/system/console/configMgr`](http://localhost:4502/system/console/configMgr) and log in.
2. Look for the configuration: `Adobe Granite Cross-Origin Resource Sharing Policy`
3. Create a new configuration with the following additional values:

   - Allowed Origins: `http://localhost:3000`
   - Supported Headers: `Authorization`
   - Allowed Methods: `OPTIONS`


## Contributing

Please see the [contributing notes](CONTRIBUTING.md).
