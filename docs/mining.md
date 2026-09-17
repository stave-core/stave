# Mining Stave (STV)

Stave uses **KawPoW**, a GPU-oriented proof-of-work algorithm. Ordinary graphics cards can take part; purpose-built hardware gains no meaningful edge because the work is re-aimed after every block.

## Requirements

- A GPU with at least 2 GB of memory (KawPoW work is memory-heavy)
- The Stave node running and synced (or a pool account)
- A Stave address to receive rewards

## Step 1 — Run a node

1. Download the wallet build from the [downloads page](https://stave-core.github.io/stave/downloads/) and verify the SHA-256.
2. Start the wallet and let it sync. The chain is the record; the block schedule you see while syncing matches the one documented on the site.
3. Create a receiving address.

## Step 2 — Choose a mode

**Pool mining** (recommended for most hardware): rewards are split among participants according to submitted shares, so income is steadier. Register with a pool running KawPoW for Stave, point your miner at the pool's stratum address and use your Stave address as the account name.

**Solo mining**: your node announces its own stratum port; point your miner at `127.0.0.1` and that port. Rewards arrive only when you cast a full block — rarer, but entirely yours.

## Step 3 — Run the miner

Any KawPoW-compatible miner works. Typical solo configuration:

```text
stratum+tcp://127.0.0.1:<your-node-port>
user: <your-stave-address>
pass: x
```

Typical pool configuration:

```text
stratum+tcp://<pool-host>:<pool-port>
user: <your-stave-address>.<worker-name>
pass: x
```

## Step 4 — Check the numbers

- Block time is 144 seconds; difficulty re-aims after every block.
- The current reward comes from the emission table in the [README](../README.md#emission-schedule) — 31 STV at step 1, halving every 480,000 blocks.
- Anything your miner reports that disagrees with the chain is the miner's problem, not the chain's.

## Notes

- Verify every archive you download against the published SHA-256.
- Running a full node while mining keeps the wall thick: your node checks every plate independently.
- Treat experimental software accordingly — keep large amounts off machines you do not control.
