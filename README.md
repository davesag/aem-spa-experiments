# aem-spa-experiments

Experimenting with Adobe Experience Manager and Single Page Apps

## See Also

- [Adobe Experience Manager](https://helpx.adobe.com/support/experience-manager/6-5.html)
- [AEM Single Page Editor](https://helpx.adobe.com/experience-manager/kt/eseminars/gems/aem-spa-editor.html) — watch the video. (approx 1 hour)
- [42 Notes - AEM SPA Editor](https://42.industrieit.com/pages/viewpage.action?spaceKey=Partners&title=AEM+SPA+Editor)
- [AEM Author in Docker](https://hub.docker.com/r/pawangonnakuti/aem-author)
- 
## Run AEM (Authoring Environment)

```sh
docker-compose up -d
```

Then point your browser at [localhost:4040](https://localhost:4040)

The first time you do this you'll be presented with a screen requesting your `customer name` and `license key`.

## Development

<!-- prettier-ignore -->
| branch | status | coverage | notes |
| ------ | ------ | -------- | ----- |
| `develop` |  |  | Work in progress |
| `master`  |  |  | Latest stable release |

### Prerequisites

- [NodeJS](htps://nodejs.org), version 10.16.3 or better (I use [`nvm`](https://github.com/creationix/nvm) to manage Node versions — `brew install nvm`.)
- [Docker](https://www.docker.com) (Use [Docker for Mac](https://docs.docker.com/docker-for-mac/), not the homebrew version)

## Contributing

Please see the [contributing notes](CONTRIBUTING.md).
