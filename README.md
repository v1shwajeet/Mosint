# MOSINT - Email OSINT Tool

MOSINT is a fast OSINT tool for emails written in Go. It helps security researchers and penetration testers gather information about the target email address through various methods and techniques.

![MOSINT Banner]

## Prerequisites

Before you begin, ensure you have the following installed:

- **Go** (version 1.16 or later)
- For macOS: `brew install go`
- For Linux: `sudo apt-get install golang-go`
- For Windows: Download from [Go Official Website](https://go.dev/dl/)
- Verify installation: `go version`

## Installation through docker 
docker build -t mosint .
docker run mosint example@example.com



## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/mosint.git
cd mosint
```

2. Navigate to the v3 directory:
```bash
cd v3
```

3. Download dependencies and build:
```bash
go mod download
go build ./cmd/mosint
```

## Configuration Setup

MOSINT requires a configuration file to work properly. Follow these steps:

1. Create a configuration file in your home directory:
```bash
cp example-config.yaml ~/.mosint.yaml
```

> ⚠️ **Important**: Never commit your `.mosint.yaml` file with real API keys to GitHub!

The configuration file supports the following API keys:
- breach_directory_api_key
- emailrep_api_key
- hunter_api_key
- intelx_api_key
- haveibeenpwned_api_key

## Usage

Basic usage:
```bash
./mosint <email>
```

Available flags:
- `--coffee` : ☕️
- `-c, --config` : Specify custom config file path
- `-h, --help` : Show help menu
- `-o, --output` : Save results to JSON file
- `-s, --silent` : Silent mode (only output file)
- `-v, --version` : Show version

Examples:
```bash
# Basic scan
./mosint example@example.com

# Save results to JSON
./mosint example@example.com -o results.json

# Use custom config file
./mosint example@example.com --config /path/to/config.yaml
```

## API Keys Setup

To unlock all features, you'll need to obtain API keys from these services:

1. **Breach Directory**: 
- Sign up at [Breach Directory](https://breachdirectory.org)
- Add key to ~/.mosint.yaml

2. **EmailRep**: 
- Register at [EmailRep](https://emailrep.io)
- Add key to ~/.mosint.yaml

3. **Hunter.io**: 
- Create account at [Hunter.io](https://hunter.io)
- Add key to ~/.mosint.yaml

4. **Intelligence X**: 
- Sign up at [Intelligence X](https://intelx.io)
- Add key to ~/.mosint.yaml

5. **HaveIBeenPwned**: 
- Get API key from [HaveIBeenPwned](https://haveibeenpwned.com/API/Key)
- Add key to ~/.mosint.yaml

## Common Issues and Solutions

1. **"unknown shorthand flag: 'e' in -e"**
- Solution: Don't use -e flag. Just provide the email directly: `./mosint example@example.com`

2. **"You must create a config file..."**
- Solution: Copy example config: `cp example-config.yaml ~/.mosint.yaml`

3. **Go installation issues**
- Solution: Verify Go installation with `go version`
- Ensure GOPATH is set correctly

4. **Build errors**
- Solution: Run `go mod download` before building
- Ensure you're in the v3 directory

## Notes

- The tool will work with basic functionality even without API keys
- Some features require specific API keys to function
- Keep your API keys private and never commit them to version control
- Regular updates may require rebuilding the tool

## Disclaimer

This tool is for educational purposes only. Users are responsible for complying with applicable laws and regulations.

