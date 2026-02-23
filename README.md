# MetaEngine OpenAPI Go net/http

[![npm version](https://img.shields.io/npm/v/@metaengine/openapi-go-nethttp.svg)](https://www.npmjs.com/package/@metaengine/openapi-go-nethttp)
[![npm downloads](https://img.shields.io/npm/dm/@metaengine/openapi-go-nethttp.svg)](https://www.npmjs.com/package/@metaengine/openapi-go-nethttp)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Generate Go net/http services and models from OpenAPI/Swagger specifications.**

Pure standard library, no frameworks. Perfect for Go projects that want type-safe API clients without third-party dependencies.

---

## Quick Links

- **NPM Package**: [@metaengine/openapi-go-nethttp](https://www.npmjs.com/package/@metaengine/openapi-go-nethttp)
- **NuGet Package**: [MetaEngine.Go.OpenApi.NetHttp](https://www.nuget.org/packages/MetaEngine.Go.OpenApi.NetHttp)
- **Website**: [metaengine.eu](https://www.metaengine.eu)

---

## Features

- ✅ **Go net/http** - Pure standard library HTTP client, no frameworks
- ✅ **context.Context** - Optional context support for all service methods
- ✅ **Pointers** - Optional pointer types for nullable fields
- ✅ **Authentication** - Bearer token, basic auth, custom headers
- ✅ **Retries** - Built-in retry support with configurable max attempts
- ✅ **Go doc** - Optional documentation comment generation
- ✅ **Tag Filtering** - Generate only the endpoints you need

---

## Installation

```bash
npm install --save-dev @metaengine/openapi-go-nethttp
```

Or use directly with npx:

```bash
npx @metaengine/openapi-go-nethttp <input> <output> <module> <package>
```

---

## Requirements

- Node.js 18.0 or later
- .NET 8.0 or later runtime ([Download](https://dotnet.microsoft.com/download))
- Go 1.21 or later (for generated code)

---

## Quick Start

### Recommended Setup

```bash
npx @metaengine/openapi-go-nethttp api.yaml ./internal/api github.com/company/project client \
  --context \
  --documentation
```

### With npm scripts

Add to your `package.json`:

```json
{
  "scripts": {
    "generate:api": "metaengine-openapi-go-nethttp api.yaml ./internal/api github.com/company/project client --context --documentation"
  }
}
```

Then run:
```bash
npm run generate:api
```

### More Examples

```bash
# From URL
npx @metaengine/openapi-go-nethttp https://api.example.com/openapi.json ./internal/api github.com/company/project client

# Filter by OpenAPI tags
npx @metaengine/openapi-go-nethttp api.yaml ./internal/api github.com/company/project client \
  --include-tags users,auth

# With bearer auth from environment variable
npx @metaengine/openapi-go-nethttp api.yaml ./internal/api github.com/company/project client \
  --context \
  --bearer-auth API_TOKEN \
  --base-url-env API_BASE_URL

# With retries and timeout
npx @metaengine/openapi-go-nethttp api.yaml ./internal/api github.com/company/project client \
  --retries 3 \
  --timeout 30

# With custom headers
npx @metaengine/openapi-go-nethttp api.yaml ./internal/api github.com/company/project client \
  --header "X-API-Version:API_VERSION_ENV"
```

---

## CLI Options

| Option | Description | Default |
|--------|-------------|---------|
| `--context` | Add context.Context as first parameter | `false` |
| `--pointers` | Use pointers for optional fields | `false` |
| `--documentation` | Generate Go doc comments | `false` |
| `--json-library <lib>` | JSON library to use | `encoding/json` |
| `--options-threshold <n>` | Parameter count for options object | - |
| `--timeout <seconds>` | Default HTTP timeout in seconds | - |
| `--base-url-env <name>` | Env var name for base URL | - |
| `--bearer-auth [env-var]` | Enable bearer auth with optional env var | - |
| `--bearer-header <name>` | Custom bearer header name | `Authorization` |
| `--basic-auth` | Enable basic authentication | `false` |
| `--retries [n]` | Enable retries with optional max count | - |
| `--header <name:env-var>` | Custom header (repeatable) | - |
| `--include-tags <tags>` | Filter by OpenAPI tags (comma-separated) | - |
| `--strict-validation` | Enable strict OpenAPI validation | `false` |
| `--clean` | Clean output directory | `false` |
| `--verbose` | Enable verbose logging | `false` |
| `--help, -h` | Show help message | - |

---

## Generated Code Structure

```
output/
  ├── models/                    # One file per model
  │   ├── user.go               # type User struct { ... }
  │   ├── product.go
  │   └── ...
  ├── services/                  # One file per service/tag
  │   ├── users_service.go      # UsersService with all user operations
  │   ├── products_service.go
  │   └── ...
  └── types.go                   # Shared type aliases and enums
```

---

## Support

- **Issues**: [GitHub Issues](https://github.com/meta-engine/openapi-go-nethttp/issues)
- **Email**: info@metaengine.eu
- **Website**: [metaengine.eu](https://www.metaengine.eu)

---

## License

MIT License - see [LICENSE](./LICENSE) file for details.

---

## About This Repository

This is the **documentation and issue tracking repository** for MetaEngine OpenAPI Go net/http. The compiled NPM package is available at [@metaengine/openapi-go-nethttp](https://www.npmjs.com/package/@metaengine/openapi-go-nethttp).

Source code is proprietary, but the package is free to use under MIT license.
