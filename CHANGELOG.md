# Changelog

See the [npm releases page](https://www.npmjs.com/package/@metaengine/openapi-go-nethttp?activeTab=versions) for detailed version history and changes.

## 0.0.2

- **New: `--bearer-auth`, `--basic-auth`, `--header`** — Authentication support with bearer tokens, basic auth, and custom headers from environment variables
- **New: `--retries`, `--timeout`** — Built-in retry and timeout configuration
- **New: `--base-url-env`** — Configure base URL via environment variable
- **New: `--include-tags`** — Filter generation by OpenAPI tags
- **New: `--strict-validation`** — Strict OpenAPI spec validation
- **New: `--clean`** — Clean output directory before generation

## 0.0.1

- Initial release with Go net/http code generation from OpenAPI specs
- `--context`, `--pointers`, `--documentation` flags
- Pure standard library output, no framework dependencies

For the complete changelog and all previous versions, visit the npm package page.
