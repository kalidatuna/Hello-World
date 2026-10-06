# Handy model shortcut bounty scope

Source: https://github.com/cjpais/Handy/discussions/746

Payer-confirmed terms by email on 2026-10-06:

- Full UI-configurable secondary shortcut scope: USD 50.
- Runtime, config, or CLI workaround scope: USD 25.
- Payment after the payer verifies the accepted build.
- PayPal is accepted.

This branch validates only the USD 25 runtime/CLI scope.

## Implemented behavior

```bash
handy --model <MODEL_ID> --toggle-transcription
handy --model <MODEL_ID> --toggle-post-process
```

The running Handy instance reads the forwarded model id, switches to that installed model before recording, and does not reload the model when it is already selected.

If the requested model cannot be switched successfully, the recording command is not fired with the wrong model.

Use `handy --list-models` to discover installed model ids.

## Scope boundary

This does not claim the remaining USD 25 UI wiring portion of the bounty.

The payer asked for the agreement to also be communicated in discussion #746. The current connected GitHub interface available to this campaign does not expose GitHub Discussions write actions, so no discussion comment is claimed.
