# Stave (STV)

**A GPU-mineable proof-of-work coin: the chain holds because the pieces match.**

A barrel holds because no single stave is special. Thin oak boards, raised and jointed edge to edge, draw tight around the contents; hoops press them together from outside, and the vessel stands for decades because every piece bears its share of the load. Remove one stave and the whole structure loosens — the strength was never in any board, it was in the arrangement. Stave is a proof-of-work cryptocurrency built on the same figure: every miner contributes one board to the barrel, the consensus rules are the hoops that press them together, and the chain holds because each new stave must fit the curve the others have already set.

- **Website:** https://stave-core.github.io/stave/
- **Downloads:** https://stave-core.github.io/stave/downloads/
- **Block explorer:** https://stave-core.github.io/stave/explorer/
- **Whitepaper:** [WHITEPAPER.md](WHITEPAPER.md)

---

## Parameters

| Parameter | Value |
|---|---|
| Name / ticker | Stave / STV |
| Algorithm | KawPoW (GPU-minable PoW) |
| Consensus | Proof-of-Work |
| Block time | 144 seconds |
| Blocks per day | 600 = 86,400 ÷ 144 |
| Block emission | 31 STV |
| Halving | every 480,000 blocks (≈ 2.19 years) |
| Maximum supply | 2 × 31 × 480,000 = **29,760,000 STV** |
| Premine / ICO | 0 / 0 |

## Emission schedule

| Step | Blocks | Per block | Minted in step | Cumulative |
|---|---|---|---|---|
| 1 | 0 – 479,999 | 31 STV | 14,880,000 | 14,880,000 |
| 2 | 480,000 – 959,999 | 15.5 STV | 7,440,000 | 22,320,000 |
| 3 | 960,000 – 1,439,999 | 7.75 STV | 3,720,000 | 26,040,000 |
| 4 | 1,440,000 – 1,919,999 | 3.875 STV | 1,860,000 | 27,900,000 |
| 5 | 1,920,000 – 2,399,999 | 1.9375 STV | 930,000 | 28,830,000 |

Past the fifth step the reward keeps halving and the supply approaches the cap of 29,760,000 STV without ever exceeding it. The schedule is a function of block height alone — it is written before the first block and cannot be changed without a visible, deliberate fork.

## Why KawPoW

KawPoW is the proof-of-work algorithm used here. It is memory-heavy and re-aimed after every block, so work cannot be folded into a fixed circuit: ordinary graphics cards can take part and purpose-built hardware gains no meaningful edge. Difficulty is retargeted every block to keep the average block time near its 144-second target.

## Repository layout

```
stave/
├── index.html            # landing page (GitHub Pages)
├── downloads/            # wallet downloads + checksums
│   └── windows/          # per-platform download pages
├── explorer/             # block explorer (static, reads chain data)
├── docs/                 # documentation
│   ├── mining.md         # pool and solo mining guide
│   ├── wallet.md         # wallet setup and usage
│   └── transparency.md   # what this project is and is not
├── WHITEPAPER.md         # protocol rationale and emission math
├── CHANGELOG.md          # release history
├── CONTRIBUTING.md       # how to take part
├── SECURITY.md           # how to report issues
├── CODE_OF_CONDUCT.md    # conduct on the repository
├── LICENSE               # MIT
└── stave.ico          # project icon
```

## Releases

Wallet builds are published as GitHub Releases **in this repository** — the release tag matches a source state, and every release page lists the SHA-256 of the archive. Verify before running:

```powershell
Get-FileHash Stave-0.1-win-x64.zip -Algorithm SHA256
```

A matching checksum proves the archive is the one published here — it is not a review. The source is open; building from source is always an option.

## Mining

KawPoW works with ordinary GPUs. The short version:

1. Run the node and let it sync.
2. Point your miner (KawPoW-stratum) at the node or a pool.
3. Collect STV to the address your node prints.

Full guide: [docs/mining.md](docs/mining.md)

## Status

Stave is experimental software, published for study. This repository describes how the network is arranged — nothing more. Read the source and draw your own conclusion, and run only the build whose checksum you have confirmed.

## License

MIT — see [LICENSE](LICENSE).
