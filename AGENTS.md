# lib-cmp

`cmp` — comparison predicates and ordering helpers (`eq`/`lt`/`gt`/
`clamp`/`min`/`max`/`compare`, sorting, range and sortedness checks).
Hybrid package: `.hnl` interface plus Rust atoms.

## Layout

| path | role |
| --- | --- |
| `src/index.hnl` | the interface — `cap`/`op` declarations |
| `src/lib.rs`, `src/ops.rs` | Rust atoms / impl crate |
| `src/docs/cmp.yml` | docs spec |
| `atoms.yaml`, `Cargo.toml`, `xtask/` | atom registry + Rust gate |
| `pkg.hnl`, `scripts/hnl-gate.sh` | manifest + `.hnl` gate |
| `workflows/gate.yaml` | CI — shared `handl-gates` campaign |

## Contract

- Transitional layout: cap/op declarations in `.hnl`, implementations
  are native atoms.
- Deps resolve from git — plain clone test-runs as-is.

## Verification

```bash
HNL=../host-cli/target/debug/hnl scripts/hnl-gate.sh
cargo xtask gate
```

<!-- myco:agent-awareness -->

## Agent awareness

- Session start / any work discussion: run `myco status --prompt`
  before proposing next steps — know the board first.
- User describes new work → offer to capture it (`myco todo add`,
  `issue new`, `proposal new`). Don't wait to be asked.
- Picking up a task: `myco resume <ID>` is the briefing.
- Wrapping up: `myco handoff <ID>` anything resumable; keep statuses
  honest (claimed → in-progress → blocked/done).

<!-- /myco:agent-awareness -->
