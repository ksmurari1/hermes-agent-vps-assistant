# Deployment and Operations

## Environment observed during setup

- Host: Hostinger VPS
- OS: Ubuntu 24.04
- Hermes Agent: v0.22.5
- Installation home: `/home/hermes/.hermes/`
- Launcher: `/home/hermes/.local/bin/hermes`
- User service: `hermes-gateway.service`
- Telegram bot: `@hermesagent_murari_bot`

## Verification commands

Check the installed version:

```bash
hermes --version
```

Check gateway status:

```bash
hermes gateway status
```

Restart the gateway gracefully using the Hermes CLI:

```bash
hermes gateway restart
```

Check the Telegram allowlist entry:

```bash
grep -n '^TELEGRAM_ALLOWED_USERS=' ~/.hermes/.env
```

Expected configuration for the currently authorized user:

```dotenv
TELEGRAM_ALLOWED_USERS=6257749053
```

The numeric ID above is specific to the current installation. Replace it with the intended Telegram user ID when reproducing this setup.

## Troubleshooting notes

### `systemctl --user` reports `Failed to connect to bus`

The user systemd bus was unavailable from the active terminal session during setup. The Hermes CLI restart command succeeded, so use `hermes gateway restart` as the first operational alternative in this environment.

### Telegram bot does not reply

1. Check `hermes gateway status`.
2. Check that the sender's Telegram ID is authorized.
3. Restart with `hermes gateway restart`.
4. Send a simple test message in Telegram.
5. Inspect recent gateway logs if it still fails.

## Reproduction notes

Installation and setup commands can change between Hermes releases. Follow the official Hermes Agent documentation for a fresh installation rather than treating this environment-specific record as a universal installer.
