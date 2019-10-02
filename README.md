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

- [Authoring: localhost:4040](https://localhost:4040)
- [Publishing: localhost:8080](https://localhost:8080)

You can log in to either with `admin` and `admin`

## Development

<!-- prettier-ignore -->
| branch | status | coverage | notes |
| ------ | ------ | -------- | ----- |
| `develop` |  |  | Work in progress |
| `master`  |  |  | Latest stable release |

### Prerequisites

- [NodeJS](https://nodejs.org), version 10.16.3 or better (I use [`nvm`](https://github.com/creationix/nvm) to manage Node versions — `brew install nvm`.)
- [Docker](https://www.docker.com) (Use [Docker for Mac](https://docs.docker.com/docker-for-mac/), not the homebrew version)

## Contributing

Please see the [contributing notes](CONTRIBUTING.md).
