# Praeterita development rules for Codex / contributors

## DO NOT CHANGE THE SNOW GLOBE HOLD POSE

**Owner-confirmed and permanently frozen unless the owner explicitly requests a change to the hold pose itself.**

The owner manually calibrated the snow globe's first-person and third-person appearance **in Minecraft**, has accepted the result, and explicitly instructed us never to adjust it again.

This applies across all future versions, refactors, feature work, bug fixes, pack rebuilds, file regeneration, and merges. Do not "improve," normalize, automatically correct, or silently reset any of the values below, even if they look unusual or do not match defaults.

The canonical configuration in `Praeterita_RP/animations/held.animation.json` must remain:

```json
{
  "format_version": "1.8.0",
  "animations": {
    "animation.praeteria.held_first": {
      "loop": true,
      "bones": {
        "root": {
          "rotation": [150, -20, 60],
          "position": [2.4, 14.5, 5],
          "scale": 0.75
        }
      }
    },
    "animation.praeteria.held_third": {
      "loop": true,
      "bones": {
        "root": {
          "rotation": [30, -10, 0],
          "position": [0, 16.5, -4],
          "scale": 0.48
        }
      }
    }
  }
}
```

Also **do not change the root bone rotation pivot** in any `Praeterita_RP/models/entity/globe_0.geo.json` through `globe_5.geo.json`. The owner-accepted root pivot is:

```json
"pivot": [0, 4, 0]
```

### Required change discipline

1. Never alter the above animation keys, transforms, scales, root pivot, or their binding when working on unrelated issues.
2. Apply the same locked configuration to all six memory-count variants (0–5). Avoid inadvertently restoring an earlier calibration while rebuilding packs.
3. If the source is missing or disagrees with this specification, do **not** choose new coordinates. Preserve the owner-approved settings during reconstruction.
4. Before any release, review `held.animation.json` and globe root pivots for accidental changes.
5. The lock may be lifted **only by a new, unambiguous, explicit request from the project owner to modify these specific hold-pose settings**. An unrelated feature request is not authorization.

**Japanese:** スノードームの持ち方（一人称・三人称の回転、位置、倍率、回転中心）はユーザー自身が実機で調整した確定仕様です。本人からその設定自体の変更を明示的に依頼されない限り、いかなる更新でも絶対に編集・上書きしないでください。

## Privacy

This is a public repository. Do not commit real player identifiers, authentication secrets, personal information, local user paths, server addresses, or private testing screenshots.
