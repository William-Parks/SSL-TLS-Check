# SSL/TLS Security Checker

This Bash tool checks a list of websites or servers for some common SSL/TLS security weaknesses. It is designed to help you quickly audit your infrastructure for outdated protocols, weak cipher suites, and certificate issues.

---

## Features

- **SWEET32 (3DES) Detection**: Checks if the server supports medium-strength 3DES cipher suites.
- **TLS 1.0 and 1.1 Detection**: Identifies support for deprecated TLS protocol versions.
- **RC4 Cipher Detection**: Flags servers that support the insecure RC4 cipher (Bar Mitzvah attack).
- **Weak Cipher Suites**: Checks for support of NULL, EXPORT, and LOW cipher suites.
- **SSL Certificate Expiry**: Reports certificate expiration date and days remaining.
- **SSL Certificate Trust**: Verifies if the certificate is trusted by your system.
- **Flexible Output**: Use `-o` to save results to a file while also displaying them in the terminal.
- **Help Option**: Use `-h` for usage information.

---

## Usage

./ssl_ssh_checker.sh [-o outputfile] [-h]


- The script will prompt you for a file containing a list of websites or servers (one per line, e.g., `example.com` or `example.com:443`).
- Use `-o outputfile` to save results to a file (output will also be shown in the terminal).
- Use `-h` to display help and usage information.

---

## Example

./ssl_ssh_checker.sh -o security_report.txt


---

## Input File Format

- Place one domain or IP per line in your input file.
- For non-standard ports, use the format `domain:port` (e.g., `example.com:8443`).

---

## Requirements

- `openssl`
- `ssh`
- Standard Unix utilities (`grep`, `date`, etc.)

All should be available on most Linux distributions by default.

---

## Disclaimer

- This tool performs active security checks. **Only scan systems you own or have explicit permission to test.**

---

## License

MIT License
