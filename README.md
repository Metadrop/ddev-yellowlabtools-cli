[![tests](https://github.com/Metadrop/ddev-yellowlabtools-cli/actions/workflows/tests.yml/badge.svg)](https://github.com/Metadrop/ddev-yellowlabtools-cli/actions/workflows/tests.yml) ![project is maintained](https://img.shields.io/maintenance/yes/2032.svg)
![GitHub Release](https://img.shields.io/github/v/release/Metadrop/ddev-yellowlabtools-cli)


# ddev-yellowlabtools-cli

A DDEV add-on that provides [YellowLabTools](https://github.com/YellowLabTools/YellowLabTools) CLI for web performance analysis directly in your DDEV environment.

## Installation

```bash
ddev add-on get Metadrop/ddev-yellowlabtools-cli
ddev restart
```

## Usage

### Basic Usage

Analyze any URL:

```bash
ddev yellowlabtools https://example.com
```

Analyze your local DDEV site:

```bash
ddev yellowlabtools local
```

### Options

| Option | Description |
|--------|-------------|
| `--device=<device>` | Device to simulate: `phone`, `tablet` (default: desktop) |
| `--screenshot=<path>` | Save screenshot to path (must end with .png) |
| `--proxy=<host:port>` | Use HTTP proxy |
| `--cookie=<value>` | Set cookie (format: `name=value; domain=.example.com`) |
| `--auth-user=<user>` | HTTP basic auth username |
| `--auth-pass=<pass>` | HTTP basic auth password |
| `--reporter=<format>` | Output format: `json` (default), `xml` |

### Examples

```bash
# Analyze local site with mobile device simulation
ddev yellowlabtools local --device=phone

# Analyze external URL and save screenshot
ddev yellowlabtools https://google.com --screenshot=/var/www/html/screenshot.png

# Analyze with HTTP basic authentication
ddev yellowlabtools https://staging.example.com --auth-user=admin --auth-pass=secret

# Save output to file
ddev yellowlabtools local > report.json
```

### Output

By default, YellowLabTools outputs JSON to stdout. You can redirect this to a file:

```bash
ddev yellowlabtools https://example.com > analysis.json
```

Or use XML format:

```bash
ddev yellowlabtools https://example.com --reporter=xml > analysis.xml
```

## What is YellowLabTools?

YellowLabTools is an open-source tool that analyzes web page performance and provides detailed reports on:

- Page weight and requests
- JavaScript execution time
- DOM complexity
- Bad practices detection
- Performance scores and recommendations

## Requirements

- DDEV v1.23.0 or higher

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

## License

Apache License 2.0
