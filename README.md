---

# restapi

A lightweight and idiomatic REST API service written in Go.
This repository contains a modular project structure with an API server entrypoint, internal application logic, configuration files, and database migrations.


## Overview

`restapi` is a Go project designed to serve as a clean foundation for building RESTful applications. The code is organized following common production-ready patterns, including a `cmd` directory for entrypoints, `internal` modules for application logic, and a `configs` directory for environment settings.

## Repository Structure

```
/cmd/apiserver      -> Entry point for the REST API server  
/configs            -> Configuration files  
/internal/app       -> Application logic: routes, handlers, services  
/migrations         -> Database schema migrations  
Makefile            -> Common build/test/run helpers  
go.mod, go.sum      -> Go modules definition  
```

## Prerequisites

* Go 1.18+ (or the version listed in `go.mod`)
* A database system (PostgreSQL/etc., depending on your config)
* `make` (optional, but recommended for convenience)

## Installation

Clone the repository:

```bash
git clone https://github.com/zxCroshka/restapi.git
cd restapi
```

Download dependencies:

```bash
go mod download
```

## Configuration

Configuration files are stored in the `configs` directory.
Before running the server, ensure that required environment variables or configuration files are set up properly — such as API port or database URL.


## Build & Run

### Run directly with Go

```bash
go run ./cmd/apiserver
```

### Build the binary

```bash
go build -o bin/apiserver ./cmd/apiserver
```

Run the binary:

```bash
./bin/apiserver
```

## API

API routes and handlers are implemented in the `internal/app` directory.
Open the source code there to see exact endpoints, request bodies, and responses.

Example request:

```bash
http -v --session=user http://localhost:8080/private/whoami "Origin: google.com"     
```

(Replace with real paths defined in your handlers.)

## Testing

Run all tests:

```bash
make test
```



