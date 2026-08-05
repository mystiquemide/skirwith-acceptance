# Skirwith acceptance repository

Public Ethereum Sepolia acceptance fixtures for the
[Skirwith](https://github.com/mystiquemide/skirwith) GitHub Action.

This repository preserves the original live evidence while the product moved
from MergePay to Skirwith. The current action has authenticated dual-read
compatibility for those historical receipts, so they remain valid proof of
replay safety rather than being silently rewritten.

## Three-state proof

- Confirmed payout: a merged pull request produces a KeeperHub USDC transfer.
- Replay: rerunning the same event resolves the existing receipt and never
  broadcasts a second transaction.
- Refusal: a merged pull request without the required label is blocked with
  `broadcastMade: false`.

## Current default-branch fixture

The current configuration and workflow use the canonical Skirwith names:

- Config: `.github/skirwith.yml`
- Required label: `skirwith-approved`
- Amount labels: `skirwith-5` and `skirwith-10`
- Receipt secret: `SKIRWITH_RECEIPT_SECRET`
- Action pin: Skirwith `v0.1.2`

The confirmed historical run is [PR #1](https://github.com/mystiquemide/skirwith-acceptance/pull/1),
with [action run 30886636409](https://github.com/mystiquemide/skirwith-acceptance/actions/runs/30886636409),
KeeperHub execution `mn7vnwz2rednekykkww8d`, and
[this Sepolia transaction](https://sepolia.etherscan.io/tx/0x4c2e25779a1bccd11db69dd68ba5aa25a5a164d3010e1a34001a55750c7dddb0).

The historical fixture descriptions remain testnet-only. No private keys,
API keys, or production funds belong in this repository.

All activity is on Ethereum Sepolia (testnet), chain `11155111`, USDC
`0x1c7d4b196cb0c7b01d743fbc6116a902379c7238`.
