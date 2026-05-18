# LeftClaw Services — Live Dashboard

A public, read-only dashboard showing live onchain metrics for LeftClaw Services.

## Live Dashboard

**[https://bafybeidio2c7zbz2ysvwg5nzfrqchawpputbf2jzhvs4ee7luawxq77bqe.ipfs.community.bgipfs.com/](https://bafybeidio2c7zbz2ysvwg5nzfrqchawpputbf2jzhvs4ee7luawxq77bqe.ipfs.community.bgipfs.com/)**

## What it shows

- **Total completed jobs** — count of all jobs with status=COMPLETE
- **Total CLAWD burned** — sum of all CLAWD tokens paid across completed jobs
- **Total revenue volume** — sum of all USD-denominated pricing for completed jobs
- **Full jobs table** — sorted newest first, with service type, CLAWD burned, revenue, date, and result link

## Architecture

Pure static HTML/JS — no server, no backend, no API keys required.

- Data pulled from the Base blockchain (chain 8453) via public RPC
- Contract: [`0xb2fb486a9569ad2c97d9c73936b46ef7fdaa413a`](https://basescan.org/address/0xb2fb486a9569ad2c97d9c73936b46ef7fdaa413a)
- Multicall3 batches all `getJob()` calls into 1-2 RPC requests
- Deployed to BGIPFS (decentralized, censorship-resistant)

## Tech stack

- ethers.js v6 (CDN) — blockchain reads
- Multicall3 (`0xcA11bde05977b3631167028862bE2a173976CA11`) — batch contract calls
- Tailwind CSS (CDN) — styling
- Public Base RPC (`https://mainnet.base.org`) — no API key needed

## Local development

Open `index.html` directly in any browser — no build step required.
