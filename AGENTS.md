# AGENTS.md

This file provides guidance to coding agents (e.g. Claude Code, claude.ai/code) when working with code in this repository.

## Repository purpose

Go module `go.bytebuilders.dev/license-tester` — a small test harness for verifying AppsCode license-issuance flows end-to-end. Used by QA / CI rather than in production.

## Architecture

- `main.go` — entry point.
- `http-checker/` — HTTP-based license-endpoint checker.
- `Dockerfile.in` (PROD, distroless), `Dockerfile.dbg` (debian).
- `hack/`, `Makefile` — AppsCode build harness.
- `vendor/` — checked-in deps.

## Common commands

- `make build` / `make all-build` — host or all-platform build.
- `make container` / `make push` — image flow.

## Conventions

- Module path is `go.bytebuilders.dev/license-tester` (vanity URL).
- License: `LICENSE.md`. Sign off commits (`git commit -s`).
- Test harness — keep additions narrow. Don't grow into a general-purpose tool.
- Two Dockerfiles, one binary — keep `Dockerfile.in` and `Dockerfile.dbg` in sync.
