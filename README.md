# vexsim-cad

The Override field shapes vexsim needs, made from VEX's field CAD. They are
made from VEX's CAD, so this repository is private and vexsim does not hold
them.

mclib's CI checks this out with a read-only deploy key and copies the four
files into its vexsim checkout's `cad/override/`.

| File | What vexsim reads it for |
| --- | --- |
| `shapes.json` | The Pin, Cup and Goal shapes the pieces collide with |
| `field.json` | Where the CAD puts the field elements and pieces |
| `view.json`, `view.bin` | The parts the 3D view draws |

## Where they come from

- STEP file: `276-9250-000 (2026-04-26).STEP`, 131,867,705 bytes, sha256
  `3f24b7572d21195522ad44f265b358bc96d0f5767920cdc6fc817c2891477a1e`.
  It is the one file in VEX's `v5rc-override-fieldcad.zip` (sha256
  `bfd460063192f2f6ee531175315eb3fdd6325bd4df35ec026c714968a81ceb5e`).
- Cut by vexsim's `tools/override_cad.py` as added in commit `6efb49e`,
  on 2026-11-04.

## Remaking them

When VEX publishes new field CAD or `tools/override_cad.py` changes, run the
tool in a vexsim checkout (vexsim's README, "Override field CAD") and copy
`shapes.json`, `field.json`, `view.json` and `view.bin` from its
`cad/override/` here. `profiles-*.json` is only for re-running the tool and
is not needed.
