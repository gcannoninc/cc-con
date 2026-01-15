# CC-Con - Central Command Console

CC-Con is a PHP console framework for building CLI tools. Part of the Central Command toolkit.

**Version:** 1.7.1

**Download:** https://github.com/gcannoninc/cc-con

## Why PHP for Console Tools?

PHP works well for console tools when:

- You already work with PHP regularly
- Your team uses PHP
- You want reusable code across web and CLI projects
- PHP is already installed on your systems
- Your use case doesn't require compilation or multi-threading

For more demanding requirements, consider Go or Rust.

## Getting Started

Clone the repository and run the executable:

```bash
git clone git@github.com:gcannoninc/cc-con.git
cd cc-con
./cc-con help
```

## Creating a New Tool

```bash
./cc-con create
```

Follow the prompts to scaffold a new tool.

## Configuration

Config files are stored in `~/.central-command/con/`

## Tools Built With CC-Con

- [CC-SSH](https://github.com/gcannoninc/cc-ssh) - Shared SSH Config Manager

## Troubleshooting

### Permission Error - Failed to write to config file

Review permissions on the config file (path in error message).

If the config file is owned by root:

```bash
sudo chown $USER:$USER ~/.central-command/con/config.hjson
sudo chmod 644 ~/.central-command/con/config.hjson
```

### Windows - SSL Errors

Download the latest CA bundle and configure PHP.ini:
- https://curl.haxx.se/docs/caextract.html
- https://www.php.net/manual/en/curl.configuration.php

### WSL - Logname Error

If you see `logname: no login name`:

```bash
sudo touch /var/run/utmp
sudo login -f yourusername
```

Then remove config files and reinstall if needed.

## License

MIT
