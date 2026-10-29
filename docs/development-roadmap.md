# Development Roadmap

## Goal

Evolve the current Telegram-connected Hermes installation into a reliable AI development assistant for Python, RAG, AutoGen, Docker, Git, and related projects.

## Milestones

### 1. Verify baseline

- [x] Hermes installed on the VPS
- [x] OpenAI API configured
- [x] Telegram bot receives and replies to a test message
- [x] Telegram user access restricted through an allowlist
- [ ] Record enabled Hermes tools and toolsets

### 2. Developer-assistant tests

- [ ] Ask for a Python debugging checklist
- [ ] Ask for a project structure and README outline
- [ ] Verify whether shell or file tools are enabled
- [ ] Test a harmless read-only task before allowing file modifications
- [ ] Confirm how tool outputs and errors are returned to Telegram

### 3. Repository workflows

- [ ] Determine whether GitHub integration is installed and authorized
- [ ] Test read-only repository inspection
- [ ] Test branch and diff review
- [ ] Keep commits and pushes as explicit, user-approved actions

### 4. Automation

- [ ] Verify scheduler support in the installed release
- [ ] Test one non-critical scheduled reminder
- [ ] Confirm timezone and Telegram delivery
- [ ] Document how to pause or remove scheduled jobs

## Acceptance criteria

A milestone is complete only after its test is run on the actual VPS and the result is recorded. Planned capabilities should not be described as active features.
