# Portal Strict Lights Patcher

A Synthesis port of the original xEdit `PortalStrictLights.pas` workflow for Skyrim Special Edition: [Portal-Strict Lights on Nexus Mods](https://www.nexusmods.com/skyrimspecialedition/mods/190892).

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

Add the following URL in Synthesis as a **Git Repository** patcher:

```text
https://github.com/hoskonen/synthesis-portalstrictlightspatcher
```

The repository also includes `PortalStrictLightsPatcher.synth` for installation through Synthesis.

During normal Synthesis use, this patcher contributes its records to the group output, `Synthesis.esp`. The dedicated `PortalStrictLightsPatch.esp` output was used only during standalone development and parity testing.

## Validation

Parity was tested on one load order with `IncludeSpotlights = false` and `IncludeMagicLights = false`. Under that configuration, the Synthesis patcher produced 149 `LIGH` overrides and its record selection matched the original xEdit patcher using the same options.

## Requirements

- Skyrim Special Edition
- Synthesis

## Possible future features

- Dry-run mode
- Optional detailed report file
