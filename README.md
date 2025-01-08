# rgeoSrv


![GitHub Actions Workflow Status](https://img.shields.io/github/actions/workflow/status/anuaimi/rgeoSrv/continuous-integration.yml) ![](https://goreportcard.com/badge/github.com/anuaimi/rgeoSrv)

![GitHub Release](https://img.shields.io/github/v/release/anuaimi/rgeoSrv)

rgeoSrv wraps the package rgeo into a reverse geocoding microservice.

See [github.com/anuaimi/rgeo](https://github.com/anuaimi/rgeo) for more
information on rgeo.

## Installation

```bash
go get github.com/anuaimi/rgeoSrv/..
```

or,

```bash
docker pull docker.pkg.github.com/anuaimi/rgeosrv/rgeosrv
```

### Usage

```bash
rgeoSrv -addr localhost:8080
```

or,

```bash
docker run -p 8080:8080 docker.pkg.github.com/anuaimi/rgeosrv/rgeosrv
```

then:

```bash
curl "localhost:8080/query?0&51.5045"
```

will return:

```json
{"country":"United Kingdom","country_long":"United Kingdom of Great Britain and Northern Ireland","country_code_2":"GB","country_code_3":"GBR","continent":"Europe","region":"Europe","subregion":"Northern Europe","province":"Tower Hamlets","province_code":"GB-TWH","city":"London"}
```

### Development

```bash
go get -u ./...
go build
docker build -t rgeosrv .
docker run -p 8080:8080 rgeosrv
curl "localhost:8080/query?0&51.5045"
```
