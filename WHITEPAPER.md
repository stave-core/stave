# Stave (STV) — Whitepaper

**A GPU-mineable proof-of-work coin: the chain holds because the pieces match.**

## 1. Introduction

A barrel holds because no single stave is special. Thin oak boards, raised and jointed edge to edge, draw tight around the contents; hoops press them together from outside, and the vessel stands for decades because every piece bears its share of the load. Remove one stave and the whole structure loosens — the strength was never in any board, it was in the arrangement. Nothing about that arrangement depends on anyone's word: the barrel either holds or it does not.

Stave is a proof-of-work cryptocurrency built on that figure. The slot is the rule set; every block is a tongue cut to fit it; the people who run full nodes check that every joint is true. Blockchains already give us an append-only record that becomes harder to rewrite the longer it stands. Stave does not add a new consensus invention on top of that. It applies the most battle-tested one — proof-of-work — with rules chosen for fairness and visibility:

- **No premine.** No coins exist before the network starts.
- **No ICO.** No tokens were sold, reserved or auctioned.
- **Fixed, public supply.** Every coin is produced by mining, on a schedule that is a function of the block height alone.

## 2. Consensus and mining

Stave uses **KawPoW**, a GPU-oriented proof-of-work algorithm. KawPoW is memory-heavy and its work is re-aimed after every block, so the work cannot be folded into a fixed circuit: ordinary graphics cards can take part and purpose-built hardware gains no meaningful edge. Difficulty is retargeted every block to keep the average block time near its target.

The choice follows from the same habit as the name. A barrel is raised by many hands in an ordinary yard — no single workshop owns the trade; an algorithm that only a few warehouses could run would contradict the design before the first block.

## 3. Parameters

| Parameter | Value |
|---|---|
| Name / ticker | Stave / STV |
| Algorithm | KawPoW |
| Block time | 144 seconds |
| Blocks per day | 600 = 86,400 ÷ 144 |
| Block emission, step 1 | 31 STV |
| Halving interval | 480,000 blocks ≈ 2.19 years |
| Maximum supply | 29,760,000 STV |
| Premine / ICO | 0 / 0 |

## 4. Emission

The reward halves every 480,000 blocks. The sum of the whole series is a closed formula:

**cap = 2 × r × h = 2 × 31 × 480,000 = 29,760,000 STV**

| Step | Blocks | Per block | Minted in step | Cumulative | Share of cap |
|---|---|---|---|---|---|
| 1 | 0 – 479,999 | 25 | 14,880,000 | 14,880,000 | 50.00% |
| 2 | 480,000 – 959,999 | 12.5 | 7,440,000 | 22,320,000 | 75.00% |
| 3 | 960,000 – 1,439,999 | 7.75 | 3,720,000 | 26,040,000 | 87.50% |
| 4 | 1,440,000 – 1,919,999 | 3.875 | 1,860,000 | 27,900,000 | 93.75% |
| 5 | 1,920,000 – 2,399,999 | 1.9375 | 930,000 | 28,830,000 | 96.88% |

Daily issuance at 600 blocks per day: step 1 — 18,600 STV/day; step 2 — 9,300; step 3 — 4,650; step 4 — 2,325; step 5 — 1,162.5.

Halving points in calendar time: block 480,000 ≈ year 2.19; block 960,000 ≈ year 4.38; block 1,440,000 ≈ year 6.57; block 1,920,000 ≈ year 8.76; block 2,400,000 ≈ year 10.95.

Past the fifth step the reward keeps halving and the supply approaches 29,760,000 STV without ever exceeding it.

## 5. Verification

Every number above can be reproduced without asking anyone:

1. Clone the source: `github.com/stave-core/stave`
2. Build the daemon and read the rule set in the code.
3. Compute 2 × 31 × 480,000 by hand and compare with the cap.
4. Compute 86,400 ÷ 144 by hand and compare with 600.
5. Run the node, let it sync, and read the block schedule from the chain itself.

## 6. Security model

The record is held by everyone who runs the software. A full node:

- checks each new block against the same test as every block before it;
- rejects any block that fails the test, whoever produced it;
- re-aims its view of difficulty from the data itself;
- accepts the heaviest chain, the way a wall settles onto the courses beneath it.

Rewriting history would require redoing the work of the entire chain faster than the honest network extends it. The economics of that trade are the security model; nothing in the protocol asks for trust in a person or a company.

## 7. Status

Stave is experimental software, published for study. This document describes how the network is arranged — nothing more. Read the source and draw your own conclusion.

## License

MIT.
