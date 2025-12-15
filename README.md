# pscp

pscp is a lightweight, cross-platform command-line tool for secure file transfers over SSH (SCP/SFTP). It aims to be fast, simple to use, and suitable for scripting and automation. This README provides installation instructions, usage examples, configuration options, and guidance for contributing.

url=https://github.com/cognitioplus/pscp/blob/1a177a7a67bc66a7bf76117c26ee6d7bad488e0d/README.md
# pscp

pscp is a lightweight, cross-platform command-line tool for secure file transfers over SSH (SCP/SFTP). It aims to be fast, simple to use, and suitable for scripting and automation. This README provides installation instructions, usage examples, configuration options, and guidance for contributing.

> Note: This README is a general, ready-to-edit template. Adjust the installation and build sections to match the actual languages, prerequisites, and packaging used by this repository.

## Table of contents

- [Features](#features)
- [Installation](#installation)
- [Quick start](#quick-start)
- [Examples](#examples)
- [Configuration](#configuration)
- [Building from source](#building-from-source)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

## Features

- Secure transfers using SSH (SCP/SFTP)
- Single-file and recursive directory transfers
- Resume interrupted transfers
- Parallel/concurrent transfers (configurable)
- Checksum verification after transfer
- Simple, script-friendly CLI with sensible defaults
- Cross-platform releases (Linux, macOS, Windows) — if provided

## Installation

Option 1 — Download a release
1. Visit the [releases page](https://github.com/cognitioplus/pscp/releases) and download the binary for your platform.
2. Place the binary on your `PATH` (for example, `/usr/local/bin` on Unix-like systems).
3. Make executable (Unix/macOS): `chmod +x /usr/local/bin/pscp`

Option 2 — Homebrew (macOS / Linux)
If a Homebrew formula is available:
```
brew install cognitioplus/pscp/pscp
```

Option 3 — Build from source
See "Building from source" below for instructions.

## Quick start

Basic remote-to-local copy:
```
pscp user@example.com:/remote/path/file.txt ./local/
```

Local-to-remote copy:
```
pscp ./local/file.txt user@example.com:/remote/path/
```

Recursive directory copy:
```
pscp -r ./local/dir user@example.com:/remote/target/
```

Specify a non-default SSH port:
```
pscp -P 2222 user@example.com:/file /local/
```

Use an identity/private key:
```
pscp -i ~/.ssh/id_rsa user@example.com:/file /local/
```

Show help and options:
```
pscp --help
```

## Examples

- Copy multiple files to remote host:
```
pscp file1.txt file2.log user@host:/var/backups/
```

- Mirror a remote directory (download) with resume:
```
pscp --resume -r user@host:/var/www/ ./www/
```

- Transfer with checksum verification:
```
pscp --checksum user@host:/data/archive.tar.gz ./archive.tar.gz
```

## Configuration

pscp reads configuration from a (optional) config file and environment variables.

Example config file (TOML/YAML/INI — adapt to actual implementation):
```toml
# ~/.pscp/config.toml
default:
  port = 22
  user = "alice"
  parallel_transfers = 4
  resume = true
```

Environment variables:
- PSCP_PORT — default SSH port
- PSCP_USER — default username
- PSCP_IDENTITY — path to default SSH key

(Modify these names to match the implementation.)

## Building from source

These are generic build steps. Replace with language-specific commands if required (e.g., `go build`, `cargo build`, `make`).

1. Clone the repository:
```
git clone https://github.com/cognitioplus/pscp.git
cd pscp
```

2. Install dependencies (if applicable)
```
# Example: npm install or go mod download
```

3. Build:
```
# Example: make build
# or: go build -o pscp ./cmd/pscp
```

4. Run tests:
```
# Example:
make test
# or:
go test ./...
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/name`
3. Make your changes and add tests where appropriate.
4. Run the test suite and linters.
5. Open a pull request against the main repository with a clear description of changes.

Please include small, focused PRs and keep commits readable. Add or update documentation when behavior changes.

## License

Specify the license for the project here (for example MIT, Apache-2.0). Add a LICENSE file to the repository.

Example:
```
MIT License
See LICENSE file for details.
```

## Support

If you find bugs or have feature requests, please open an issue on the repository: [Issues · cognitioplus/pscp](https://github.com/cognitioplus/pscp/issues)

For urgent or private support, include contact instructions here.

---

If you want, I can adapt this README to match the project's actual implementation (language, build tool, exact CLI flags and config schema). Provide details (language, how to build, CLI options) and I will update the README accordingly.
````

> Note: This README is a general, ready-to-edit template. Adjust the installation and build sections to match the actual languages, prerequisites, and packaging used by this repository.

## Table of contents

- [Features](#features)
- [Installation](#installation)
- [Quick start](#quick-start)
- [Examples](#examples)
- [Configuration](#configuration)
- [Building from source](#building-from-source)
- [Contributing](#contributing)
- [License](#license)
- [Support](#support)

## Features

- Secure transfers using SSH (SCP/SFTP)
- Single-file and recursive directory transfers
- Resume interrupted transfers
- Parallel/concurrent transfers (configurable)
- Checksum verification after transfer
- Simple, script-friendly CLI with sensible defaults
- Cross-platform releases (Linux, macOS, Windows) — if provided

## Installation

Option 1 — Download a release
1. Visit the [releases page](https://github.com/cognitioplus/pscp/releases) and download the binary for your platform.
2. Place the binary on your `PATH` (for example, `/usr/local/bin` on Unix-like systems).
3. Make executable (Unix/macOS): `chmod +x /usr/local/bin/pscp`

Option 2 — Homebrew (macOS / Linux)
If a Homebrew formula is available:
```
brew install cognitioplus/pscp/pscp
```

Option 3 — Build from source
See "Building from source" below for instructions.

## Quick start

Basic remote-to-local copy:
```
pscp user@example.com:/remote/path/file.txt ./local/
```

Local-to-remote copy:
```
pscp ./local/file.txt user@example.com:/remote/path/
```

Recursive directory copy:
```
pscp -r ./local/dir user@example.com:/remote/target/
```

Specify a non-default SSH port:
```
pscp -P 2222 user@example.com:/file /local/
```

Use an identity/private key:
```
pscp -i ~/.ssh/id_rsa user@example.com:/file /local/
```

Show help and options:
```
pscp --help
```

## Examples

- Copy multiple files to remote host:
```
pscp file1.txt file2.log user@host:/var/backups/
```

- Mirror a remote directory (download) with resume:
```
pscp --resume -r user@host:/var/www/ ./www/
```

- Transfer with checksum verification:
```
pscp --checksum user@host:/data/archive.tar.gz ./archive.tar.gz
```

## Configuration

pscp reads configuration from a (optional) config file and environment variables.

Example config file (TOML/YAML/INI — adapt to actual implementation):
```toml
# ~/.pscp/config.toml
default:
  port = 22
  user = "alice"
  parallel_transfers = 4
  resume = true
```

Environment variables:
- PSCP_PORT — default SSH port
- PSCP_USER — default username
- PSCP_IDENTITY — path to default SSH key

(Modify these names to match the implementation.)

## Building from source

These are generic build steps. Replace with language-specific commands if required (e.g., `go build`, `cargo build`, `make`).

1. Clone the repository:
```
git clone https://github.com/cognitioplus/pscp.git
cd pscp
```

2. Install dependencies (if applicable)
```
# Example: npm install or go mod download
```

3. Build:
```
# Example: make build
# or: go build -o pscp ./cmd/pscp
```

4. Run tests:
```
# Example:
make test
# or:
go test ./...
```

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/name`
3. Make your changes and add tests where appropriate.
4. Run the test suite and linters.
5. Open a pull request against the main repository with a clear description of changes.

Please include small, focused PRs and keep commits readable. Add or update documentation when behavior changes.

## License

Specify the license for the project here (for example MIT, Apache-2.0). Add a LICENSE file to the repository.

Example:
```
MIT License
See LICENSE file for details.
```

## Support

If you find bugs or have feature requests, please open an issue on the repository: [Issues · cognitioplus/pscp](https://github.com/cognitioplus/pscp/issues)

For urgent or private support, include contact instructions here.
