<p align="center"><a href="https://valkyrja.io" target="_blank">
    <img src="https://raw.githubusercontent.com/valkyrjaio/art/refs/heads/26.x/long-banner/orange/go.png" width="100%">
</a></p>

# Valkyrja Starter (App)

Starter application for building Go applications on the [Valkyrja][Valkyrja url]
framework.

The complete starter gives you a working Valkyrja application as a starting
point. It passes the same formatting, static analysis, and architectural rules
as the Valkyrja framework itself. You build your application, not the foundation
under it.

<p>
    <a href="https://github.com/valkyrjaio/valkyrja-starter-app-go/blob/26.x/go.mod"><img src="https://img.shields.io/badge/Go-1.26-orange" alt="Go Version"></a>
    <a href="https://github.com/valkyrjaio/valkyrja-starter-app-go/blob/26.x/LICENSE.md"><img src="https://img.shields.io/github/license/valkyrjaio/valkyrja-starter-app-go.svg" alt="License"></a>
    <a href="https://github.com/valkyrjaio/valkyrja-starter-app-go/actions/workflows/ci.yml?query=branch%3A26.x"><img src="https://github.com/valkyrjaio/valkyrja-starter-app-go/actions/workflows/ci.yml/badge.svg?branch=26.x" alt="CI Status"></a>
    <a href="https://coveralls.io/github/valkyrjaio/valkyrja-starter-app-go?branch=26.x"><img src="https://coveralls.io/repos/github/valkyrjaio/valkyrja-starter-app-go/badge.svg?branch=26.x" alt="Coverage Status"></a>
    <a href="https://sonarcloud.io/summary/new_code?id=valkyrjaio_valkyrja-starter-app-go"><img src="https://sonarcloud.io/api/project_badges/measure?project=valkyrjaio_valkyrja-starter-app-go&metric=sqale_rating" alt="Maintainability Rating"></a>
</p>

Port Status
-----------

The Go port is in progress, and this repository holds the scaffolding for it.
The starter follows the framework, so an entry point arrives here after the
component it drives lands in [`valkyrja-go`][framework url]. Read
[`PORTS.md`][ports url] for the state of each port.

The sections below describe the starter that every port provides. A file is not
in this repository until its own package exists.

What's in the Box
-----------------

Warning: the CI gate is the only item below that this repository holds today.
`app/` and `cmd/` are both absent, and each remaining item arrives with the
component it needs.

- **The full CI gate** — the same formatting, static analysis, and coverage
  rules the framework holds itself to. This item is here now.
- **Pre-wired HTTP and CLI entry points** — the application boots and answers
  both web requests and command-line invocations
- **Example controllers and commands** — working code that shows routing,
  request handling, and command dispatch
- **Configuration scaffolding** — an `AppConfig` that the build tool reads, and
  that names the component providers the application registers

Installation
------------

### Use This Template _(recommended)_

This repository is a GitHub template. Click **Use this template** at the top of
the repository page to create your own application, pre-populated with the
structure and the CI.

### Clone Manually _(for contributing to the starter itself)_

```bash
git clone https://github.com/valkyrjaio/valkyrja-starter-app-go.git
cd valkyrja-starter-app-go
go mod download
```

Getting Started
---------------

### Project Structure

The `app` package holds your application. The entry points are grouped by
protocol, and the runtime is named in the type rather than in the directory, so
one protocol keeps one package:

```
app/
├── http/       HTTP configuration, controllers, routes, and providers
└── cli/        CLI configuration, commands, routes, and providers
cmd/
├── public/     the HTTP entry point
└── bin/        the CLI entry point
```

### Running Your Application

Warning: `cmd/public` and `cmd/bin` arrive with the entry points, and this
repository holds neither yet. The commands below are what you will run once they
land.

```bash
go run ./cmd/public
go run ./cmd/bin
```

### Running Tests

```bash
make test
```

### Running CI Checks Locally

The gate is the same one CI runs:

```bash
make ci
```

That runs the module tidiness check, the shared golangci-lint configuration, the
copyright header check, the tests, and the coverage floor.

Documentation
-------------

Valkyrja documentation is baked into the framework repository so you can browse
it offline. See the [Valkyrja framework repository][framework url].

The build tool that generates the application's data structs is
[Sindri][sindri url].

Contributing
------------

This starter is an open-source, community-driven project. Thank you for your
interest in helping develop, maintain, and release it.

See [`CONTRIBUTING.md`][contributing url] for the submission process and
[`VOCABULARY.md`][vocabulary url] for the terminology used across Valkyrja.

Security Issues
---------------

If you discover a security vulnerability within this starter, please follow our
[disclosure procedure][security vulnerabilities url].

License
-------

This starter is open-source software licensed under the
[MIT license][MIT license url]. See [`LICENSE.md`](./LICENSE.md).

[Valkyrja url]: https://valkyrja.io
[framework url]: https://github.com/valkyrjaio/valkyrja-go
[sindri url]: https://github.com/valkyrjaio/sindri-go
[ports url]: https://github.com/valkyrjaio/architecture/blob/26.x/PORTS.md
[contributing url]: https://github.com/valkyrjaio/.github/blob/26.x/CONTRIBUTING.md
[vocabulary url]: https://github.com/valkyrjaio/.github/blob/26.x/VOCABULARY.md
[security vulnerabilities url]: https://github.com/valkyrjaio/.github/blob/26.x/SECURITY.md
[MIT license url]: https://opensource.org/licenses/MIT
