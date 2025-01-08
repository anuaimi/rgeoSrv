# rgeoSrv

[![](https://img.shields.io/github/workflow/status/anuaimi/rgeoSrv/continuous-integration?style=for-the-badge)](https://github.com/anuaimi/rgeoSrv/actions?query=workflow%3Acontinuous-integration)
[![](https://goreportcard.com/badge/github.com/anuaimi/rgeoSrv?style=for-the-badge)](https://goreportcard.com/report/github.com/anuaimi/rgeoSrv)
[![Release](https://img.shields.io/github/tag/anuaimi/rgeoSrv.svg?label=release&color=24B898&logo=github&style=for-the-badge)](https://github.com/anuaimi/rgeoSrv/releases/latest)
[![go.dev reference](https://img.shields.io/badge/go.dev-reference-007d9c?logo=go&logoColor=white&style=for-the-badge)](https://pkg.go.dev/github.com/anuaimi/rgeoSrv)

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
