# Handy model shortcut bounty scope

Source: https://github.com/cjpais/Handy/discussions/746

Payer-confirmed terms by email on 2026-10-06:

- Full UI-configurable secondary shortcut scope: USD 50.
- Runtime, config, or CLI workaround scope: USD 25.
- Payment after the payer verifies the accepted build.
- PayPal is accepted.

This branch now contains both the previously delivered runtime/CLI evidence and
the remaining USD 25 UI wiring implementation.

## Implemented behavior

```bash
handy --model <MODEL_ID> --toggle-transcription
handy --model <MODEL_ID> --toggle-post-process
```

The running Handy instance reads the forwarded model id, switches to that installed model before recording, and does not reload the model when it is already selected.

If the requested model cannot be switched successfully, the recording command is not fired with the wrong model.

Use `handy --list-models` to discover installed model ids.

## UI wiring added

handy-ui.patch applies to Handy commit
a94b403e0610049fafa54b0a4077db2945084dd8 and adds:

- a second configurable transcription shortcut in General settings;
- a model selector for the primary shortcut;
- a model selector for the secondary shortcut;
- persisted, independent primary and secondary shortcut model choices;
- model switching at the actual recording-start boundary, so a secondary
  shortcut does not redefine the primary shortcut's selected model;
- normal Handy shortcut activation behavior for both transcription shortcuts;
- translation keys across every locale so translation-key validation remains
  consistent.

The workflow applies the patch to the pinned upstream commit and validates Rust
formatting, frontend formatting, translation keys, TypeScript/Vite build,
frontend lint, secondary shortcut routing, default shortcut parsing, and
git diff --check.

## Scope boundary

The remaining USD 25 UI wiring portion is implemented by handy-ui.patch.

The payer asked for the agreement to also be communicated in discussion #746. The current connected GitHub interface available to this campaign does not expose GitHub Discussions write actions, so no discussion comment is claimed.
