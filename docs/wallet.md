# Stave Wallet — setup and usage

## Download and verify

1. Get the build from the [downloads page](https://stave-core.github.io/stave/downloads/).
2. Verify the checksum in PowerShell:

```powershell
Get-FileHash Stave-0.1-win-x64.zip -Algorithm SHA256
```

3. Compare the output with the SHA-256 printed on the download page. It must match exactly.

## First start

1. Unpack the archive and run the wallet.
2. The wallet starts syncing. Sync state and peer count are shown in the status bar; the chain is the record, and the schedule it follows matches the one documented on the site.
3. Create a receiving address from the *Receive* tab. Addresses are free — make a new one for each purpose if you prefer.

## Backup

- The wallet file lives in the data directory the wallet prints on first start.
- Copy it to storage you control while the wallet is closed.
- The backup is the coins: whoever holds the file holds the balance, so store it where a fire would not reach both copies.

## Receiving and sending

- *Receive*: pick an address, share it; incoming plates appear after the first confirmation.
- *Send*: paste the destination address, check the first characters, confirm. Transactions are final once sufficiently deep in the chain — there is no undo.

## Notes

- A matching checksum proves the archive is the one published here — it is not a review. Building from source is always an option.
- If the wallet behaves strangely, compare what it reports with what a second full node reports. The chain is the arbiter, not the interface.
