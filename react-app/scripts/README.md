# README

```console
. ./scripts/react-app-new
./scripts/docker-build
./scripts/docker-start
```

modify package.json - remove "react-app/jest

```json
"eslintConfig": {
    "extends": [
      "react-app"
    ]
  },
```

- docker image
  - <https://medium.com/swlh/how-we-reduced-react-docker-image-by-17x-cd684898470f>
- investigate
  - <https://shemleong.medium.com/using-docker-and-yarn-for-development-2546e567ad2>