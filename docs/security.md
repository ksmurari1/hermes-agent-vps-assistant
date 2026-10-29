# Security

## Secrets

Never commit or share:

- OpenAI API keys
- Telegram bot tokens
- `.env` files or `~/.hermes/.env`
- Private configuration files containing secrets
- Logs that may contain personal data, tokens, or private messages

## Telegram access

The current setup restricts access using `TELEGRAM_ALLOWED_USERS` in `~/.hermes/.env`.

Example:

```dotenv
TELEGRAM_ALLOWED_USERS=YOUR_TELEGRAM_USER_ID
```

Use the actual Telegram **user** ID, not the bot's ID. Keep the list limited to intended users.

## Pairing versus allowlisting

Allowlisting and pairing are different authorization paths. The current working setup uses an allowlist. A successful bot reply does not mean that the pairing-code workflow was used. If pairing is required, review the installed Hermes version's official documentation and deliberately configure that workflow before removing the existing working access control.

## Tool permissions

Before enabling shell, file, browser, Git, or other tools:

1. Understand what the tool can read and change.
2. Prefer least-privilege access.
3. Test with a harmless task first.
4. Require confirmation before destructive or external side-effect actions.
5. Avoid exposing private repository content or credentials in Telegram messages.

## Repository hygiene

Before every push, inspect staged files:

```bash
git status --short
git diff --cached --stat
```

Make sure secrets and private logs are not staged.
