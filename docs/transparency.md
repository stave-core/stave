# Transparency

This page states plainly what the Stave project is and what it is not.

## What is fixed before the first block

- The complete emission schedule: 31 STV per block at step 1, halving every 480,000 blocks, cap 2 × 31 × 480,000 = 29,760,000 STV.
- The block time: 144 seconds, with difficulty re-aimed after every block.
- The algorithm: KawPoW, chosen so ordinary GPUs can take part.
- The rule set: the source code, open under MIT, is the single specification.

None of these are promises about future behaviour; they are the rules the software enforces today, and any change would be a visible, deliberate fork of the source.

## What does not exist

- No premine: no coins existed before the network started.
- No ICO, token sale, auction or reserve of any kind.
- No founder allocation and no development fee baked into the block reward.
- No official price prediction, trading advice or yield claims — anywhere, by design.

## How releases relate to source

Each release tag in this repository corresponds to a state of the source. Release pages list the SHA-256 of every archive. Verify before running; a matching checksum proves the archive is the one published here, not that the software is perfect.

## Governance

The repository is the process. Anyone can read the code, open issues, and propose changes through pull requests. What ships is what the maintainers merge — and what ships is always inspectable after the fact.

## Status

Stave is experimental software, published for study. This repository describes how the network is arranged — nothing more. Read the source and draw your own conclusion.
