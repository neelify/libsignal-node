# Changelog

## v1.0.33

### 🔐 Decrypt diagnostics (additive, behind a flag)

- Added structured decrypt-failure classification inside `decryptWithSessions`
  (`session_mismatch` / `already_decrypted` / `possible_corruption`), additive and
  rate-limited, gated behind `ONIMAI_LOG_SIGNAL_DECRYPT_WARN=1`.
- **No behavioural change**: nothing is deleted or reset. Multi-session decrypt and the
  existing Bad-MAC "try the next session" path stay intact — a Bad MAC across several
  sessions is a normal mismatch, not corruption.
- Helps distinguish benign session mismatch / duplicate delivery (already decrypted)
  from a genuine single-session corruption case.

## v1.0.32-ecosystem-clean

### 💖 Neelegirly Ecosystem Clean Stability Update

- Removed workspace/core confusion from documentation.
- Clarified the 4-package architecture.
- Clarified that PM2 only runs the app.
- Clarified that WA-API handles sessions internally.
- Improved beginner-facing usage documentation.
