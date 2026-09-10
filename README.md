# Portal Strict Lights Patcher

A Synthesis port of the original xEdit `PortalStrictLights.pas` workflow for Skyrim Special Edition.

The patcher processes winning `LIGH` records and creates overrides that set Portal-strict in both locations used by the game data:

- `Light.Flag.PortalStrict`
- `Light.MajorFlag.PortalStrict`

Deleted records are ignored, and lights that already have both flags are skipped.

## Settings

| Setting | Default | Description |
| --- | --- | --- |
| `IncludeSpotlights` | `false` | Include lights carrying `Light.Flag.SpotLight` or `Light.Flag.ShadowSpotlight`. |
| `IncludeMagicLights` | `false` | Include lights whose EditorID contains `"magic"`, matched case-insensitively. |

## Installation and use

Install through Synthesis as a **Git Repository** patcher. The repository also includes `PortalStrictLightsPatcher.synth` for installation through Synthesis.

During normal Synthesis use, this patcher contributes its records to the group output, `Synthesis.esp`. The dedicated `PortalStrictLightsPatch.esp` output was used only during standalone development and parity testing.

## Validation

With both optional settings disabled, the patcher produced 149 light overrides on the tested load order. Its record selection matched the original xEdit patcher on the same load order.

## Requirements

- Skyrim Special Edition
- Synthesis

Current development baseline: .NET 10, Mutagen.Bethesda.Skyrim 0.54.4, and Mutagen.Bethesda.Synthesis 0.36.6.

## Future ideas

- Dry-run mode
- Optional detailed report file
