# MergePay Acceptance Repository

Private testnet repository for Phase 3 live three-state acceptance of the
[MergePay](https://github.com/mystiquemide/mergepay) GitHub Action.

- Confirmed payout: a merged pull request labeled `mergepay-approved` +
  `mergepay-5` pays 5 USDC on Ethereum Sepolia.
- Replay: re-running the same event resolves the existing receipt and never
  broadcasts a second transaction.
- Refusal: a merged pull request without the required label is blocked with
  `broadcastMade: false`.

All activity is on Ethereum Sepolia (testnet), chain `11155111`, USDC
`0x1c7d4b196cb0c7b01d743fbc6116a902379c7238`. Trusted configuration lives in
`.github/mergepay.yml` on the default branch.
